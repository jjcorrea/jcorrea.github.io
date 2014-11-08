---
layout: post
title: Architectural styles
---

Given the importance, and the growing need of dealing with **quality** and **maintainability** targets, through software architecture techniques (as exposed on the [previous post]({% post_url 2014-11-03-architecture-oriented-development %})), there are categorizations of architectural styles which supports the required characteristics of software systems. 

The **architectural styles** use clear **terminologies**, **properties** and **restrictions** to identify the components (a.k.a subsystems) and interaction mechanisms between them, what is specially usefull for software engineers to **reuse** the architectural patterns on scenarios in which they are needed. 

Each **style** supports a set of **non-functional requirements** and **project attributes** what makes possible distinguish between different architectures.

<br />
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

<br />
To be continued...




