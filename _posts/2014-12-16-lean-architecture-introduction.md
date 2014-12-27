---
layout: post
title: Lean architecture - Introduction
---

## Touchstones: Lean & Agile

- Buzzwords ahead.
- 90s management culture = Toyota way / Lean term coined
- **Value stream** = primary focus = "Every single activity adds value"
- Waste *reduces* value. Constant improvement *increases* value
- "All hands on deck" mentality = **Team**
- Agile manifesto enphasizes the **customer**, Lean = **stakeholders** (everybody in sight)
- Not about working: harder, "smarter", but more about **focus** and **discipline**.
- The architecture should support the company **value stream**
- *Just in time deliver* instead of *stockpilling* software library warehouses = **Continuous flow**

- Source code itself should reflect the end-user mental model of the world
- Continuous flow
- Team mentality

### Lightweight architecture

Arch with reduced waste incurred by:

- Rework (inadequate planning)
- Unused artifacts (such as comprehensive documentation and **speculative code**).
- Wait states (handoffs between functional teams, review lifecycle of arch / design documents)

### People say architecture is hard

- Complexity
- Takes-a-long-time vs Complexity
- Unite specialists, everybody all together, from early on
- Neither lean nor agile make architecture look easy, but they illuminate the architecture's value

### Architecture value

Lean brings that:

- Careful, up-front planning
- "Everybody, all together, from early on"
- How the architecture can **reduce waste**, **inconsistency** and **irregular development**

Agile:

- Feedback
- How user **engagement and feedback** can drive down long-term cost


## Lean architecture and Agile feature development

- Classic approach embraces engineering *too early* = Rushes into implementation.
- Lean + Agile encourages changes in those parts of the system which are likely to change - because they aren't pre-filled with premature structures
- Standards are valuable at level of form, protocols and APIs rather than their implementation
- Agile = Communication and sometimes written documentation in the right medium

## Agile production

### Agile builds on Lean

- Agile production plans for **change**. Stakeholder changes can be propagated without being lost.
- Agile stays lean with its focus on code. **Code isn't the design**. The code is the vest way to capture the end-user mental model, and the techniques, problem solving strategies are part of the **design** process.
- Lean: value sream starts with end-users = Agile: Individuals and interactions over processes and tools.

### The scope of agile systems

- Architecture = Stability. Agile = Change
- Plan for change (70s, 80s) vs Change directly
- "User **expectation** as the father of change"
- Modern markets = Speed = Adaptation
- Agile adapts to this market due to its accomodation for change
- Fits independently of the feedback value: Formally specified systems (little value) vs No obvious interaction between systems (high value)
- "Lean is an overkill for simple systems"
- Agile can draw on lean to estabilish the boundary conditions necessary for **progress** 

### Highlights

- Software architecture should reflect the end-user mental model of the world
- System **form**: Users thought process while viewing the screen, and *what the system is*
- System **functionality**: How the system respond to user input, *what the system do*
- Stakeholders (early) insight exploration
- Code expresses *form* concretely
- Communication


