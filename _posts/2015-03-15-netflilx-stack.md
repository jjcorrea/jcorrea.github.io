---
layout: post
title: Netflix Stack
---

A summary of the Netflix open source tools. Categorizes into:

- **Availability**: [Hystrix](/2015/03/15/netflix-stack-hystrix/), [SimianArmy](/2015/03/15/netflix-stack-simian-army/), [Turbine](/2015/03/15/netflix-stack-turbine/)
- **Cloud Management**: ICE, Asgard, Frigga, Glisten
- **Persistence Systems**: Astyanax, CassJMeter, Curator, EvCache, Exhibitor, Priam, Staash, Dynomite, Dyno, Raigad
- **Platform libraries**: Archaius, Denominator, Feign, Karyon, [Ribbon](/2015/03/15/netflix-stack-ribbon/), Servo, Blitz4J, Governator
- **Infrastructure Services**: Atlas, Edda, Suro, Eureka, Zuul, Prana
- **Developer productivity**: GCViz, Pytheas, Nicobar
- **Build and Deploy tools**: Aminator
- **Big Data tools**: Aegisthus, Genie, Inviso, Lipstick, Pigpen, S3mper, Surus
- **In memory data management**: Netflix-graph, Zeno
- **Security**: MSL, Scumblr, Security_Monkey, Sketchy
- **Sample applications and recipes**: Recipes RSS

## Availability

### Hystrix

A **latency and fault tolerance** library designed to isolate points of access to remote systems, services and 3rd party libraries, stop cascading failure and enable resilience in complex distributed systems where failure is inevitable.

### SimianArmy

Tools for keeping your cloud operating in top form. Chaos Monkey is a resiliency tool that helps applications tolerate random instance failures.

### Turbine

SSE Stream Aggregator

## Cloud Management

### Ice

AWS Usage Tool

### Asgard

Web interface for application deployments and cloud management in Amazon Web Services (AWS). Binary download: http://github.com/Netflix/asgard/releases Snapshot builds: https://netflixoss.ci.cloudbees.com/job/asgard-master/ Twitter: http://twitter.com/AsgardOSS
http://netflix.github.com/asgard

### Frigga

Utilities for working with Asgard named objects

### Glisten

Ease of use Groovy library for building JVM applications with Amazon Simple Workflow (SWF)

## Persistence Systems

### Astyanax

Cassandra Java Client

### CassJMeter

JMeter plugin to run cassandra tests.

### Curator

ZooKeeper client wrapper and rich ZooKeeper framework.

### EVCache

A distributed in-memory data store for the cloud

### Exhibitor

ZooKeeper co-process for instance monitoring, backup/recovery, cleanup and visualization.

### Priam

Co-Process for backup/recovery, Token Management, and Centralized Configuration management for Cassandra.

### Staash

A language-agnostic as well as storage-agnostic web interface for storing data into persistent storage systems, the metadata layer abstracts a lot of storage details and the pattern automation APIs take care of automating common data access patterns. 

### Dynomite

A generic dynamo implementation for different k-v storage engines 

### Dyno

Java client for Dynomite.

### Raigad

Co-Process for backup/recovery, Auto Deployments and Centralized Configuration management for ElasticSearch.

## Platform Libraries

### Archaius

Library for configuration management API

### Denominator

Portably control DNS clouds using java or bash.

### Feign

Feign makes writing java http clients easier.

### Karyon

The nucleus or the base container for Applications and Services built using the NetflixOSS ecosystem.

### Ribbon

Ribbon is a Inter Process Communication (remote procedure calls) library with built in software load balancers. The primary usage model involves REST calls with various serialization scheme support.

### Servo

Netflix Application Monitoring Library.

### Blitz4j

Logging framework for fast asynchronous logging.

### Governator

Governator is a library of extensions and utilities that enhance Google Guice to provide: classpath scanning and automatic binding, lifecycle management, configuration to field mapping, field validation and parallelized object warmup.

## Infrastructure Services

### Atlas

Backend for managing dimensional time series data.

### Edda

Service to track changes in your cloud.

### Suro

Netflix's distributed Data Pipeline. Suro is a data pipeline service for collecting, aggregating, and dispatching large volume of application events including log data.

### Eureka

AWS Service registry for resilient mid-tier load balancing and failover.

### Zuul

Zuul is an edge service that provides dynamic routing, monitoring, resiliency, security, and more.

### Prana

A sidecar for your NetflixOSS based services.

## Developer Productivity

### Gcviz

Garbage Collector Visualization Tool/Framework

### Pytheas

Web Resources and UI Framework 

### Nicobar

Dynamic Scripting and Module Loader Framework for Java.

## Build and Deploy Tools

### Aminator

A tool for creating EBS AMIs. This tool currently works for CentOS/RedHat Linux images and is intended to run on an EC2 instance.

## Big Data Tools

### Aegisthus

A Bulk Data Pipeline out of Cassandra

### Genie

Federated Job Execution Engine.

### Inviso

Inviso is a lightweight tool that provides the ability to search for Hadoop jobs, visualize the performance, and view cluster utilization.

### Lipstick

Pig Visualization framework.

### PigPen

Map-Reduce for Clojure.

### S3mper

s3mper - Consistent Listing for S3.

### Surus

A collection of tools for analysis in Pig and Hive.

## In-Memory Data Management

### Netflix-Graph

Compact in-memory representation of directed graph data

### Zeno

Netflix's In-Memory Data Propagation Framework.

## Security

### Msl

Message Security Layer.

### Scumblr

Web application that allows performing periodic searches and storing / taking actions on the identified results. Uses the Workflowable gem to allow setting up flexible workflows for different types of results.

### Security_monkey

Monitors policy changes and alerts on insecure configurations in an AWS account. 

### Sketchy

Sketchy is a task based API for taking screenshots and scraping text from websites.

## Sample Applications and Recipes

### Recipes-Rss

RSS Reader Recipes that uses several of the Netflix OSS components

## Uncategorized

### NfWebCrypto

Web Cryptography API Polyfill 

### Brutal

A multi-network asynchronous chat bot framework using twisted.
