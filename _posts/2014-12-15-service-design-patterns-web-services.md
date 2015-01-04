---
layout: post
title: Service design patterns - Web services
---

Challenges:

- When should a particular api style be used
- client-service **communication** + foundations for complex conversations (multiple parties, extended periods of time)
- Approaches for implementing service **logic**
- **Decoupling** clients from the underlying systems used by the service
- Discover **information about a service**
- How to support generic functions (authentication, validation, caching) on client / service
- Service changes which **break clients**
- **Version** services
- Support continuous evolution (business logic) without requiring users to **upgrade**

## What are Webservices

- Software function which carries a **business task**, provide access to files or perform generic functions (authenticating, logging, etc)
- Many different stacks
- Share logical functions
- **Webservices** integrate disparate systems and **expose reusable business functions** over HTTP
- Either leverage to HTTP as simple **transport** over which the data is transfered (SOAP/WSDL) or use it as a complete application protocol that defines the **semantics** for service behavior (RESTful services) 

## From local objects to distributed objects

- Objects = encapsulate behavior (e.g **business logic**) and **data**
- White-box **reuse** = access objects internals
- **State** between client calls
- **Components** = group related objects into deployable binary software units, that can be plugged into applications. Blackbox reuse - normally not accessible internal objects.
- **Remoting** technologies to support distribution (e.g. CORBA, DCOM, Java RMI)
- Complex implementation. 
- Lack of standards (different vendor toolkits had problems to communicate).

## State issue

Distributed objects typically maintained state between client calls, what led to a number of **scalability** problems.

- Memory utilization degradation with increased client load
- Effective load balance difficulty: User state was hold on a single server, coupling the user to that specific node.
- Server needs to implement a strategy to free memory


## Why Webservices

- Share common logic with different clients (mobile, desktop, web apps)
- Open standards: independent on the underlying technologies. 
- Facilitate complex business processes through **composition** - possible assembling simple services into workflows
- Clients and services may evolve independently = **indirection** = **isolation**

### When to use

- Client and service belongs to different domains
- Service functions cannot be easily imported on client
- Client is a complex business process
- Separation between clients and services is natural.

## Downs

- Expensive calls (e.g serialization / desserialization)
- Network latency
- **Partial failures**: Client, service or network fails while the others continue operating - requires strategies to detect and handle them

## Alternatives

- Service libraries: Imported and executed on the client application
- If client and service were implemented on different platforms, there are ways to integrate them (e.g. JNI / Third-party bridging techniques).
- Network overhead (high-performance / high-load scenario). A **connectionless protocol like UDP** may be an alternative.
- HTTP is Good for large documents / messages. There are better alternatives for real-time delivery, such as RTSP (real time streaming protocol), RTP (real time transport protocol), RTCP (real time control protocol).

## Loose coupling

- There will be always some sort of coupling
- Function coupling: Clients indirectly depend on the service implementation.
- Data structure coupling: Clients need to know which are the input / output formats, encoding, http status codes, etc.
- Temporal coupling: Occurs when the message needs to be processed as soon as it is received. Synchronous (blocking) processes increase this kind of coupling, and asynchronous processes reduces it, despite it adds complexity
- URI coupling: Clients are normally tighly coupled to service URIs. There are a number of patterns to reduce this coupling, as Linked service, service connector, etc.


To be continued...

