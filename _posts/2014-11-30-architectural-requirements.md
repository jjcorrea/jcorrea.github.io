---
layout: post
title: Architectural requirements
---

Generally the set of system requirements are defined during the initial steps of the development cycle. It should be seen as the **specification** of what needs to be implemented. The requirements are descriptions of how the system should **behave**, contains **domain information** and **restrictions** about the system operation.

During the requirement elucidation phase the software architect / engineer tries to identify the system'm specificities which needs to be supported. Once the set of requirements is obtained, it is then posssible to start the architectural project.

The software development process based on the architecture puts the architecture as a **guidance**, as the **orientation** factor of the process, so we can also say that in an architecture oriented development the requirements are part of the main aspects of the development process.

The system **complexity** can be determined by its **functional requirements** - what it does - and by its **quality / non-functional requirements** - how it does. The distinction can be done using the following definitions:

## Functional requirement
A software requirement which specifies a **funcionality** that the system or a software component needs to be able to perform. This requirements define the system **behavior**, in other words, the transformation process that software or hardware components do on the inputs to generate the outputs (Thayer, 1990).

## Quality / Non-functional requirement
Describes **how** the software performs its tasks, not what it does. Thus, there are the *performance* requirements, *restrictions* and software *quality* attributes. Non-functional requirements are difficult to test, then they are normally evaluated subjectively (Thayer, 1990).

## Project attributes
There are several **principles** which guide the software development process, focused on obtaining a final product which satisfies the identified requirements during the process. They are called project attributes.


### Separation of concerns (SOC)
The separation of concerns allows to deal ith *different aspects of a problem* focusing in each of them **isolatedly**. This idea can be applied in order to deal with inherent complexity. The separation of concerns has been applied when a system is **decomposed** in several modules, with the architecture containing more than one component. 

In this case it allows to separate or isolate part of the system functionality, but how can we determine *which part of the system should be separated*? The interest to isolate specific components and its functionalities comes from the target to provide support to a set of quality requirements. So, doing a separation in terms of the system quality requirements is essential to support them appropriately. 

### Abstraction
One of the main ways to deal with complexity. It is, in fact, a process in which we can *identify the important aspects of some phenomenon and ignore its details*. Abstraction can also be seen as a special case of SOC, where we separate the important aspects concern of the non-important details. By doing so, the engineers can concentrate in what they judge relevant and ignore the details.

### Modularization
When software engineers face a big / complex system they generally divide them into smaller pieces or **modules** A system composed by a set of modules is called **modular**. 

One of the main benefits of this attribute is that it allows SOC being applied in two steps:

1. When dealing with each module details isolatedly, and then ignoring other modules details
2. When dealing with general characteristics of all modules, and the existing relations between them, enabling integrating them into a system. 

There are three targets that modularization tries to obtain:

- **Decompose** a big / complex system
- **Compose** a system using a set of modules
- Understand the system modularization

Its important to notice that a modular system implies in modules with a high level of **cohesion** and low level of **coupling**, what allows to consider the modules as black boxes.

### Resources sharing
In modular systems, the components should have a low level of coupling ideally, as it can become difficult to analyze, comprehend, change, test and even reuse highly coupled systems. However, it still possible to have low coupled components even when sharing resources. The resources can be *data or services* which are shared across several **independent** components. 

Notice that sharing resources normally implies in increasing the **integration** and **portability** of systems.

## Non-functional requirements
Non-functional requirements have a main role during the system development, they may be used as selection criteria for project alternatives, architectural style and implementation method.
Disregard, of not consider this requirements properly is **admittedly expensive** and makes it difficult to correct once the system has been implemented (Brooks, 1987).

Consider the [IEEE-Std 830-1993](http://www.utdallas.edu/~chung/RE/IEEE830-1993.pdf) (IEEE, 1993) standard. It lists a set of 13 non-functional requirements to be considered in software requirement specification. This pattern includes **performance** requirements, **reliability**, **portability** & **security**, similarly to another classification presented by Boehm, who looked to list a set of, what he nominated, quality requirements (Boehm, 1976).

The following picture is an adaptation of Sommerville classification (Sommervile, 1992) summarizes a set of quality requirements important to consider:

![Non-functional requirements](/assets/non-functional-requirements.png)

### Usability
A quality requirement  of any **interactive** system. Usability notion comes from the fact that any system designed to be used by people should be easy to **learn** and **use**, making it easier and enjoyable to perform any task.

- Ease to learn: Associated to the time and minimal efford required to reach a given level of performance using the system.
- Ease to use: Related to the task execution speed and reduction of errors while using a system.

Some relevant usability metrics:

1. Time spent performing a task
2. Task completion percentage
3. Task completion percentage by time unit
4. Success / failure rates
5. Time consumed by errors
6. Error percentage
7. Number of commands used
8. Number of commands available not used
9. 'Help' usage frequency
10. Number of times the user expresses he's satisfaction or frustation

### Maintainability
A quality requirement normally applied when refering to changes done after the system is available to use. It is a wide term, involving **repair** (of some existing error), as **change / evolution** activities.

The ease of change, adding or modifying some functionality, depends directly on the system architecture. Its important to notice that the architecture define the components and their connections, then also defines under which circumstances they can be changed.

### Reliability
Software reliability is a property of a software not causing a failure during a certain amount of time, under specific conditions. The reliability is generally defined on **statistical behavior**, it is the probability that a software *will operate as expected* during a known interval.

Some of the metrics used to evaluate software reliability:

- **Availability**: Its a metric of how available the system would be, in other words, how much available the system would be to perform a task requested by some user.
- **Failure rate**: A metric for calculating the *frequency in which the system fails* in performing a task requested by a user.
- **Failure probability** during operational phase: Metric of the probability that a system will behave in an unexpected way while operating.
- [Mean time to failure (MTTF)](http://en.wikipedia.org/wiki/Mean_time_between_failures#MTTF_and_MTTFd_calculation): Metric of time between observable failures.

### Performance
Another important quality attribute for software systems. Given the impact it can cause, the performance requirements in the most important quality requirements. Furthermore, performance is important because it affects the system **usability**, impacting then the users **productivity**.

The performance requirement restricts the speed of operation of a software system. This can be seen, for example, in terms of:

- **Response requirements**: Indicates a acceptable response time for system users.
- **Throughput requirements**: Indicates the amount of data that should be processed in a certain time period.

### Reuse

One of the characteristics of engineering is to make use of existing projects to minimize the efford of new projects. On this way, components which have been already developed and tested could be reused. 

The reuse can be seen on different perspectives. It can be component oriented, process oriented or domain specific. There can be also requirements reuse. About component reuse, it can happen in some of the following ways:

- **Application**: All application could be reused.
- **Subsystems**: The main subsystems of an application could be reused.
- **Objects or modules**: System components, containing a set of functions, could be reused.
- **Functions**: Components which implement a single function could be reused.


<hr />

This post basically walked through a generic process of architectural requirements analysis. The outcome of this process is a set of **functional requirements**, supported by **use cases**, a list of **architectural requirements**, **project attributes** and **quality (non-functional)** requirements, which indicate **how** the system will behave under different **quality scenarios**.
