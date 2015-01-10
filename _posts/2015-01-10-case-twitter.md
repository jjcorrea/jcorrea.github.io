---
layout: post
title: Twitter architecture overview
---


## Cache

- Clear need for caching. Each tweet is tracked in average by 126 users
- On original configuration, the API have a cache, which was invalidated each time a tweet was coming from a user.
- 1st change: Create a **Vector Cache** containing an array of tweet IDs - **99% hit rate**
- 2nd change: **Row Cache** containing database records: *users and tweets* - **95% hit rate**
- 3rd change: **Fragment Cache** containing **serialized versions** of the tweets accessed through API clients, packaged in JSON, XML or Atom - **95% hit rate**
- 80% of the Twitter traffic comes through the API
- Because of poor request locality, the fastest way to deal with requests is to **precompute data** and **store it on network RAM**, rather than recompute it on each server when necessary

## Message queue

- Twitter’s MQ is simple: based on Memcached protocol, no ordering of jobs, no shared state between servers, all  is kept in RAM and it is transactional.
- First implementation of the MQ was using Starling, written in Ruby. Didn't scale well.
- Ruby’s GC is **not generational**, which means that the *GC looks at every object every time it runs*. Java, OCaml, and other static languages have a **generational GC**, which means that only *recent allocations are frequently checked*.
- That lead to MQ crashes because at some point the entire **queue processing stopped for the GC** to finish its job
- The decision was to **port the MQ to Scala** which is using the **more mature JVM GC**.

## Data store

### Original tweeet store

- Temporal sharding. Tweets from the same date range are stored on the same shard.
- The problem is tweets filled up one machine, then a second, and then a third. You end up filling up one machine after another.

### Flaws

- **Load balancing**. Most of the old machines didn't get any traffic because people are interested in what is happening now, especially with Twitter. 
- **Expensive**. They filled up one machine, with all its replication slaves, every three weeks, which is an expensive setup.
- **Logistically complicated**. Building a whole new cluster every three weeks is a pain for the DBA team


## The new data store

- When a tweet is created it is stored in a system called **T-bird**, which is built in the top of [Gizzard](https://github.com/twitter/gizzard) - Twitter's distributed data storage framework built on top of MySQL (InnoDB). 
- Secondary indexes are stored in **T-flock**, also based on Gizzard.
- To get **higher performance on individual nodes** a lot of features like *binary logs* and *replication* are **turned off**.
- Gizzard handles sharding, replicating N copes of the data, and job scheduling. 
- [Snowflake](https://github.com/twitter/snowflake) for generating tweet **unique IDs**


## Highlights

- Twitter values **stability over features** so they've stayed with older releases. 
- MySQL doesn't work for *ID generation* and *graph storage*
- **Cassandra** is used for *high velocity writes*, and *lower velocity reads*. The advantage is Cassandra can run on *cheaper hardware than MySQL*, it can expand easier, and they like *schemaless design*.
- **Hadoop** is used to process **unstructured** and **large datasets**, hundreds of billions of rows.
- **Vertica** is being used for analytics and **large aggregations and joins** so they don't have to write MapReduce jobs
- **Soft launches**: Features can be enabled / disabled

## References

- http://highscalability.com/blog/2011/12/19/how-twitter-stores-250-million-tweets-a-day-using-mysql.html
- http://www.infoq.com/news/2009/06/Twitter-Architecture
- http://blog.evanweaver.com/2009/04/09/ruby-gc-tuning/