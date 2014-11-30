---
layout: post
title: Architectural styles
---

Given the importance, and the growing need of dealing with **quality** and **maintainability** targets, through software architecture techniques (as exposed on the [previous post]({% post_url 2014-11-03-architecture-oriented-development %})), there are categorizations of architectural styles which supports the required characteristics of software systems. 

The **architectural styles** use clear **terminologies**, **properties** and **restrictions** to identify the components (a.k.a subsystems) and interaction mechanisms between them, what is specially usefull for software engineers to **reuse** the architectural patterns on scenarios in which they are needed. 

Each **style** supports a set of **non-functional requirements** and **project attributes** what makes possible distinguish between different architectures.

## #1 Pipes and filters

Characteristics:

- Data flow which goes from an edge (**origin**) to another (**destination**)
- Data is processed and transformed on **filters**
- **Unidirectional** flow = Operations chaining

An example of pipes and filters would be the following UNIX command:

{% highlight bash %}
sample$ who | sort
{% endhighlight %}

The result of *who* is a list of currently connected users, and its output is used as the input of *sort*, which orders the values alphabetically.

![Unix who | sort](/assets/arch-styles-pipe-and-filter.png)

The two programs, *who* and *sort* are **components** called **filters**. Notice that the filters can start putting the transformation outcome on the pipes *before all the input data is processed*, and that the sort output could lead to another filter represented on the picture by the dotted box.

Another example of pipes & filters architectural style can be found at the classical *compilers* model. The first compilers used to work in two steps: *source language analysis* and *code synthesis* (Aho, 1987). With the hardware evolution, the need of **portability** started raising, and the classical model needed to be enhanced to a new process, composed by 3-legged analysis (lexical, syntactic & semantic analysis), and 2-step synthesis (optimization & generation).

It is worth to comment that this architectural style is normally **flexible**, enabling the pipes and filters reorganization. Although this style provides *maintainability* support in terms of easy reorganization, it is clear that frequent changes on a component (filter) can impact the other components, so maintainability support is limited on this style.

## #2 Layers

The **layered** architectural style structures a system into a set of layers, where each of them groups a set of *tasks* in a certain level of *abstraction*. 

In a layered architecture, a layer on the N level normally offers a set of functionalities to the above level (N + 1). N uses its functions as well as it uses the functionality provided by the below layer (n - 1). 

A variation of this style could enable the N layer to access N-2, N-3 and so on, but notice that doing so the system **maintainability can be affected**. Having a bigger dependency level between layers imply on more layers to be changed once having a new requirement or change. 

A good example of this style is the **OSI** (Open Systems Interconnection) reference model (Tanenbaum, 1988). On this model each *layer* can be seen as a *component* which can be implemented by software or hardware. It is composed by 7 layers and serves as the computer network protocol architecture.

- 7. Application
- 6. Presentation
- 5. Session
- 4. Transport
- 3. Network
- 2. Data link
- 1. Physical

In fact a layered architecture gives a higher level of *flexibility*, however this has an associate **cost** on the system **performance**, as an external request needs to pass through many layers in order to be handled. Anyway, implementing a **monolithic** system / protocol isn't an appropriate solution as well.

## #3 Implicit invocation (Event driven)

Differently than the architectural style based on objects, on which one object (component) invokes the other directly through message passing, the implicit invocation style requires the components interested on an **event** *registering* themselves in order to receive it. In this case, the system provides a mechanism for forwarding the events to the registered components.

## #4 Blackboard

The blackboard architectural style emerged on artificial intelligence field, in which it was used as a mechanism for sharing the knowlege (data) between many intelligent components. This style considers the existence of a main data **repository** surrounded by a set of components called knowlege sources (KSs).

The blackboard architectural style is based on a sproblem solving model which provides a conceptual structure for organizing the domain knowlege as well as a strategy to apply that knowlege.

The style consists on 3 basic components:

- **Knowlege sources**: The knowlege needed for solving a problem is partitioned in knowlege sources. Each source is **separated** and **independant**.
- **Blackboard data structure**: The problem solving data is maintained in a **shared database**, called blackboard. The knowlege sources causes modifications on the blackboard, what triggers changes until having a final **solution**. All interactions and communication between sources occurs only though this blackboard.
- **Control**: The knowlege sources **reacts** to changes on the blackboard.

![Blackboard organization](/assets/arch-styles-blackboard.png)

This architectural style is recommented on applications where several types of knowlege should be considered in order to interpret a set of initial data. It was tipically used on cases where there was *no general solution* for a problem. One or more components (KSs) interacts with the shared database (blackboard) looking for a **partial** or **total** solution for the problem (in the case of a *partial solution*, another component can be activated then).

## #5 Distributed systems

There are several architectural models in which regards distributed systems. We are going to see two of the most common styles: **Multiprocessor** and **multicomputer**.

A **multiprocessor** architecture comprehends many processors *sharing* a primary memory. This style is appropriate to *execute several subtasks simultaneously* in a *same program*. On the other hand, a **multicomputer** architecture is similar to multiprocessors, except that the processors *doesn't share memory*.

![Distributed system](/assets/arch-styles-distributed.png)

The distributed system consists on *multiple processors* which uses message passing mechanisms to communicate to each other. In other words, a distributed application can be seen as a concurrent program in which the processes communicate through message passing. Consists on four (4) types of processes (components):

- **Filter**: A data *transformer*. Receives a data flow as input, runs computations and put the outcomes on the output
- **Client**: Can be seen as a *process*. In a client-server interaction, a *client* is a component which starts some activity.
- **Server**: Different than a client, a *server* waits for client requests to handle them. In other words, a server is a **reactive** process.
- **Peer**: One in a set of identical processes which interacts to offer some service or perform some parallel computation.

## #6 Communicating processes

Fits in the set of distributed application architectures. The communicating processes style is used when the priority goals of the system are **scalability** and **ease of change**.

An example is a system in which there is a set replicated of **workers** (computational components) which share a single task repository. Different than descentralized servers which holds multiple *copies of data*, this style provides several *copies of the components*.

This style is used in parallel systems when dealing with the [SIMD](http://en.wikipedia.org/wiki/SIMD) (Single Instruction, Multiple Data) paradigm.

## #7 Client-Server

Another architectural style which fits in distributed architectures is client-server. This style allows the tasks being divided between data **producers** and **consumers**. A *server* is a process which waits for requests from one or more *clients*.

- Ease of removing and / or adding clients, due to the processes *independence*.
- Ease of changing *client functionalities* given other clients are not affected.

## Style variations

There is a significant amount of architectural styles nowadays, and there are also variations of that styles. When presenting a style it is important to notice the system **non-functional / quality requirements**, which can be for example:

- Ease of change
- Maintainability
- Reliability
- Availability
- Extensibility
- Fault tolerance
- Interoperability
- Resilience
- Security

It is important to notice that in practice a system architecture is almost never obtained from a single style. Given that, a software architect needs to understand the *relationships* between styles, what requires knowing the project **attributes**, **non-functional requirements** as well as requires an **architectural analysis** process, anwering questions like:

- Which is the architectural style **topology**?
- How does the **data transfer** and / or **control** occurs between components?
- Which type of components and **connectors** are used on this style?
- How is the control shared between components?
- Is there some interaction between data and control?
- Has the type of analysis have any influence on the style?
- Does the components interact **synchronously** or **asynchronously**?

One of the main aspects of an architectural project is the use of system **organization patterns**. Many of this patterns, also called **architectural styles**, have been developed across the time once software engineers recognized the value of organization and structure principles for certain categories of software.



