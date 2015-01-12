---
layout: post
title: Requirement patterns catalog
---


## Inter-system Interface requirement pattern


> Specify basic details for an interface between the system being specified and any external system or component with which it needs to interact.


- Use for external interfaces, not for internal
- Interaction
- Exchange of information
- Unique interface ID
- Different systems treated separately
- Interface adapters
- Interface ownership


### Extra requirements

#### Throughput

How much traffic must the interface be able to handle?

#### Scalability

How well must the interface deal with increases in thoughput?

#### Extendability

Do you need to be able to slot extra interfaces of this type?

#### Resilience and availability

How well and how quickly must the interface recover from failure? Identify anomalies and deal with them. During what hours it needs to be running?

#### Traffic verification and recording

Must we be abke ti tekk exactky what was sent and received?

#### Upgrading

What happens when the interface changes? Versioning.

#### Security

Are we worried about strangers getting their hands on the information that is passing along the interface?


## Inter-system Interaction requirement pattern

> Specify a particular type of interaction across an inter-system interface

- Each interface involves a range of different interactions.
- The interface may hold a number of business related functions, but might also possess a number of more technical and supporting interactions
- Interaction type = Exchange of a particular type of information

### Considerations for testing

-  Formulate both valid and invalid (erroneous) cases
- Try to cover as representative a spread of situations as possible 




