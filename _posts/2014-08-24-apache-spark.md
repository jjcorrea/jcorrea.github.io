---
layout: post
title: Apache Spark
---

Version checked <span class="label label-default">1.0.2</span>

> An open-source clustered data analytics framework

### Highlights

<span class="label label-primary">Cluster computing</span>
<span class="label label-primary">Scala, Java & Python API</span>
<span class="label label-primary">Analytics</span>
<span class="label label-primary">Batch processing</span>
<span class="label label-primary">Stream processing (Real time)</span>

### Trade-off
<span class="label label-success">Spark SQL</span> 
<span class="label label-success">MLib</span> 
<span class="label label-success">GraphX</span> 
<span class="label label-success">Spark Streaming</span> 
<span class="label label-warning">Storage = Hadoop FS</span>
<span class="label label-warning">Shared variables</span>
<span class="label label-danger">?</span>

## Overview
http://spark.apache.org/docs/latest/programming-guide.html

The main spark abstraction provides RDDs (**Resilient distributed dataset**) - A collection of elements **partitioned** across the nodes of a cluster, which can be operated in **parallel**.

RDDs are created by starting with a file in **Hadoop filesystem** (or any other *Hadoop supported filesystem*), it is possible to persist RDD **in memory**, allowing it to be reused efficiently across parallel operations. RDDs also **recover node failures**.

There is also the notion of **shared variables**. which *can be used* in parallel operations. Two possible types:

1. **Broadcast variables** - Cache a value in memory (all nodes)
2. **Accumulators** - Counters, Sums, etc

![RDD](/assets/spark-rdd.png)


## Shell
http://spark.apache.org/docs/latest/sql-programming-guide.html

## Spark SQL
http://spark.apache.org/docs/latest/sql-programming-guide.html

## MLib
http://spark.apache.org/docs/latest/mllib-guide.html

## GraphX
http://spark.apache.org/docs/latest/graphx-programming-guide.html

## Cluster mode
http://spark.apache.org/docs/latest/cluster-overview.html

## Spark Streaming
http://spark.apache.org/docs/latest/streaming-programming-guide.html

