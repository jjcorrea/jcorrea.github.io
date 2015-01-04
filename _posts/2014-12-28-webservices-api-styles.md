---
layout: post
title: Webservices API styles
---

- Distinct APIs
- Attend multiple client types
- API reflecting client needs (top-down)
- External vs Internal API

## Design considerations

### Encapsulation

- Services should **hide implementation details**
- Prevents **coupling** the clients
- Service design should avoid exposing its internals
- "Bottom-up" design if making domain entities accessible to external clients
- **Indirection** enables internals evolve or even to be replaced

### Service contract

- **Agreement** on how clients and services may interact
- Pre / Post **conditions** indicating the client **expectations**

### Autonomy

- **Dependencies** on outside forces
- External entities, services, etc
- Distributed transactions

### Latency

- **Serialization / Deserialization** cost
- **Network**
- Payload size
- Few **"chunky" messages** are normally better than "chatty conversation" (several smaller messages)

### Partial failures

- **Failure scenarios handling**
- "Clients need to be prepared to service failures and vice-versa"

### Binary message encoding of text-based data

- Information exchanged is generally text-based
- Text information may be **encoded as binary** data before being serialized
- **Compression**

## RPC API

> How can clients execute remote procedures over HTTP?

- Not easy (low-level communication protocols)
- Different platforms use different **encodings**
- Remoting technologies (CORBA, DCOM) made it easier to share and use remote procedures
- Request: Procedure(i.e. service) name + arguments
- Response: Procedure results
- Service frameworks: JAX-WS & WCF for abstracting structural formats (JSON / XML), encoding, generating XSD, etc

### Considerations

- **Flat APIs** inclination: Tendency to create service signatures just as class method signatures
- **Breaking changes**: Argument order - Add, remove and reorder breaks the client
- Single-Message argument pattern to resolve the issue (+ flexibility)
- **Proxies** and **service descriptors**: Clients applications typically use proxies to connect to services on this style. Typically reads service descriptors (e.g. WSDL)
- Location transparency
- Async: RPC APIs often use **request-acknowlege** instead of **request-response** interaction pattern. 
- Avoid blocking: Clients can use an **async response handler** pattern to avoid being blocked during the service processment

## Message API

> How can clients send commands, notifications or other information to remote systems over HTTP while avoiding direct coupling to remote procedures

- Signature changes may be breaking
- Determines the procedure based on message content
- Style is normally used when external entities **drive the requirements** definition
- Messages are typycally defined using XML Schema language, however messages can be defined through other means (e.g. Google protocol buffers / ProtoBuff).
- API provides **endpoints**
- Messages are generically of three types: *Command messages* (triggers a specific task on the receiver) *Event messages* (notify) or *Document messages* (like business documents).
- WSDL as **service descriptor** and for **specifications** (WS-Policy, WS-Security, etc)

### Considerations

- **Service descriptors and connectors**: Message APIs often employ a **service descriptor** 
(most common is WSDL) to aid in client-side **connectors**. Operations are grouped into an abstract type (an *interface* on WSDL 2.0)
- **Delegation of work**: The logic used to process specific message types is often triggered by a **command invoker** - when the logic is sufficiently complicated. An alternative is to use a **workflow connector** - when triggering a complex, long-running job.
- Async: Message APIs often use **request-acknowlege** instead of **request-response** interaction pattern. 
- Avoid blocking: Clients can use an **async response handler** pattern to avoid being blocked during the service processment
- Late binding: Often provide addresses to related services clients may use

## Resource API

A client application that consumes or manipulates text, images, documents or other media files managed by a remote system.

> How can a client manipulate data managed by remote system, avoid direct coupling to remote procedures, and minimize the need for domain-specific API

- Provides access to resources (media file, collection of related data, database information, a logical transaction, etc)
- Often adhere to REST
- Since each URI refers to a single resource / collection, services can often be added, changed or removed with **minimal impact**
- Contracts are composed of: protocol, media types produced or consumed by the service, status codes, and URI schemes to identify the resources.


### Considerations

- Use with **disparate clients**: Good choice when having a wide mix of clients
- **Addressability**: Make it easy to save and share links to services
- Code generation of service connectors: Client developers can't take advantage of code generation tools (no service descriptors).
- **Async**: Resource APIs often use **request-response**, but can use **request-acknowlege** interaction pattern as well. 
- Avoid **blocking**: Clients can use an **async response handler** pattern to avoid being blocked during the service processment
- Support to client **preferences**: Supports multiple representation of the same resource. Rather than a different URI, you can use **media type negotiation** to enable clients to indicate their preferences.
- Late binding: Often provide addresses to related services clients may use
- Ability to leverage commodity **caching** technologies
- Resources API and REST: Not every Resource API adhere to REST, but they often do.