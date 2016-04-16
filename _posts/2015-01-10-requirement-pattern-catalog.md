---
layout: post
title: Requirement patterns catalog
---

<br />
## Fundamental requirement patterns

### Inter-system Interface

> Specify basic details for an **interface (exchange of information) between the system being specified and any <u>external</u> system** or component with which it needs to interact.

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

<br />
<hr />
<br />

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

<br/>

<hr />

<br/>
## Data Entity



<br/>

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


<br/>

<hr />

<br/>

## User function

<br/>

### Inquiry

> Define a screen display function that shows specified information to the user.

### Report

> Define a report that shows specified information to the user. The information being displayed is not modified by the report - although it might involve some background generation of data.

### Accessibility

> Specify the extend to which the system (or part of it) must be accessible by people with **certain kind of disability** or other specific need - That is, how convenient it must be for them to use.

### User interface infrastructure

> Coherent set of components that together enable a user to interact with the system

### Reporting infrastructure

> Produces reports for us and usually lets us design new reports.

<br/>

<hr />

<br/>

## Performance

<br/>

### Response time

> **How long** it takes to the system to satisfy requests

### Throughput

> The **rate** at which the system can process things

### Dynamic capacity

> **How many things** the system can cope with and work at once

### Static capacity

> **How many entities of a particular type** the system can store

### Availability

> **When the system is available to users** and how reliably

<br/>

<hr />

<br/>

## Flexibility

<br/>

### Scalability

> Ready to cope with **increases in business volumes**

### Extendability

> Able to **plug in extra software** easily

### Unparochialness

> Avoid limitations **preventing installation elsewhere** (by another company, in another region, or country, and so on)

### Multiness

> Support **multiple companies, currencies** at the same time

### Multi-lingual

> Supports user interfaces in **multiple languages** at the same type

### Installability

> How easy the system must be to **install**

<br/>

<hr />

<br/>

## Access control

<br/>

### User registration

> **Making people known** to the system

### Authentication

> **Recognizing** a user as a known person

### Authorization

> What a user is **allowed to do and see**

### Specific authorization

> Concrete user **authorization rules**

### Configurable authorization

> Insisting that definitions of who can do, what can be changed dynamically

### Approval

> Forcing selected actions **to be approved by a second person**

<br/>

<hr />

<br/>

## Commercial

<br/>

### Multi organization unit

> **Accomodating the way a business structures** itself (multiple departments, offices, companies and so on)

### Fee / tax

> Ways to **charge** people money

<br/>

<hr />

<br/>


## References

- Book: Software requirement patterns - Best practices. Stephen Withall
