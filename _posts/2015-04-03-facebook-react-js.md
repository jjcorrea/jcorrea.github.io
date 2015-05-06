---
layout: post
title: Facebook - React JS
---

## Topics
- Virtual DOM
- Interactive vs Reactive
- Observable

### Interactive
- Passive: exposes functions so others can change it
- Proactive: changes and forces passive modules

#### Passive is BAD
- "Someone else is responsible for me."

### Roles in Reactive Programming
- Reactive: listens to events, and exposes events that can listened by others
- No other role
- "I am in full control over myself."

### What is react?
- Virtual DOM Rendering
- Reusable hierarchical components
- Hides Virtual DOM data structure from the programmer
- Mostly Passive API
- Not a framework, an opinionated building block
- **React virtual elements are not observable**

### Criticism
- Great ideas, bad API
- React is not Reactive Programming
- Rendering is Reactive, all the rest is Passive
- React is unsuitable for Reactive Programming
- React could be better

## Virtual DOM alternatives
- https://github.com/Raynos/mercury
- http://lhorie.github.io/mithril/ (MVC)

## References
- http://staltz.com/dont-react/
