---
layout: post
title: Agile production
---

## Stakeholders engagement

- Stakeholders = Team members, engineers, architects, testers...
- What the system is = Architecture / Platform. Stable structures of the business over time. **Key stakeholders are**: Domain experts, system architects, business people.
- What the system does = End user's view of the services provided by the system. **Key stakeholders are**: End user, UX, interface designers, requirements folks.
- Remember lean: "everybody, all together, from early on"
- Customer engagement is one of the strongest agile principles

## Problem definition

- "The difference between the current state and the desired state"
- Short description - if everyone knows what the problem is, everyone knows when it is done
- Revisit the problem definition once in a while

## What the system is - System form

- "Every system has two designs (reflects two kinds of intents): The design of its functionalities - what it *does* and the design of its form - what it *is*"
- The form provides a firm **foundation* for change*
- The **structure** of a system follows its form
- The **end-user mental model** is one sound foundation for architecture

We do architecture:

1. To **capture stakeholders perspectives** that affect design
2. To **embrace change** and **reduce the cost of solving problems**
3. To create a **shared vision** across the team & stakeholders
4. To **smooth the decision making** process

**"Good form up front reduces cost in long term"**

## What the system does - System functionality

- Captures end-user mental model as **roles** or **actors**, and by the interaction between these roles.
- **Use cases** capture role and its interactions as well. Good tool for elicit, explore, refine and capture end-user mental models and also for organizing requirements (functional grouping, mutual dependency and priority ordering).
- A sound architecture provides a context in which users scenarios can unfold.
- The scenarios have two parts: The pure business logic and the domain logic that supports the scenario
- Testers pay close heed to what the system **is supposed to**

## Design and Code

The main activities at this point are:

1. Turn use case scenarios into algorithms.
2. Write system tests
3. Tailor the domain class interfaces to the new algorithms
4. Code up the algorithms in the role code and the support logic in the domain code (+refactoring along the way)
5. Run the newly written system tests against the new code

