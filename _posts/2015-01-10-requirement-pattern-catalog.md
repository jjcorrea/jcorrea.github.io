---
layout: post
title: Requirement patterns catalog
---

## Fundamental requirement patterns

### Inter-system Interface

> Specify basic details for an **interface (exchange of information) between the system being specified and any <u>external</u> system** or component with which it needs to interact.

Extra requirements

- Throughput: How much traffic? 
- Scalability: How well must the interface deal with increases in throughput?
- Resilience and availability: How quickly must the interface recover from failure? During what hours it needs to be running?
- Upgrading: What happens when the interface changes? Must we be able to support old and new versions?
- Security: Are we worried about strangers getting their hands on the information that is passing, along the interface?

### Inter-system Interaction

> Specify a particular type of **interaction** across an inter-system interface

### Technology

> **Compatibility** with particular technology

### Comply-with-Standard

> Standards, Laws and Regulations **to comply** with

### Refer-to-Requirements

> **External requirements** to be satisfied

### Documentation

> **Types of documentation** to be produced

<hr />

## Information Requirement patterns

### Data type

> How a particular atomic item of information for a particular business purpose is to be represented and / or displayed 

### Data structure

> Define a compound data item (one that comprises multiple individual pieces of information)

### ID

> How to identify data entities

### Calculation formula

> How to calculate values

### Data longevity

> How long to keep the information

- Manner of storage?
- Length of time to retain the data?
- Purpose: Why do we want to keep this information for this length of time?

### Data archiving

> Specify the moving or copying from one place of permanent storage to another

<hr />

## Data Entity

> Features common to all types of information

### Living Entity

> Entities that have a lifespan

### Transaction

> Events in the life of living entities

### Configuration

> Parameters that control how system behaves

### Chronicle

> Record of system events (logs, audit trails)

### Information Storage infrastructure

> Infrastructure to store the information (eg database)




