---
layout: post
title: Requirement pattern concepts
---

> "Each pattern describes a problem which occurs over and over again in our environment" - Christopher Alexander

- Projects have requirements which are **similar** in nature
- **Requirement pattern**: An approach for specifying a particular **type of requirement**
- **Follow-on** requirements: Expand the original requirement
- **Pervasive** requirements: Supports the pattern itself 
- Patterns can vary on their **level of detail** (their **preciseness**)

Benefits of requirement patterns:

1. **Guidance**: Suggests information to include, advices, warning of common pitfalls.
2. **Time save**: Don't have to write each requirement from **scratch**, gives a suitable starting point, a foundation to build on.
3. **Consistency** across requirements of the same **type**


## The anatomy of a requirement pattern

- What it contains, how it is organized and why
- A requirement pattern needs to say **when to use it**, **how to write requirements based on it**. Can also give hints on how to **implement** and how to **test** it.

To convey these sorts of information, each requirement pattern should contain

1. **Basic details**: Pattern classification, author, related patterns, etc
2. **Applicability**: In what situations can this pattern be applied?
3. **Discussion**: How to write a requirement of this type? What needs to be considered?
4. **Content**: What must a requirement of this type say?
5. **Template(s)**: Starting point for writing a requirement of this type
6. **Example(s)**: One or more representative examples
7. **Extra requirements**: What sorts of requirements often **follow on**
8. **Considerations for development**: Hints for software designers and engineers on how to implement a requirement of this type
9. **Considerations for testing**: What do we need to bear in mind when deciding how to test this type of requirement?

## Domain

- For classifying the requirement patterns, instead of having a monolithic list of them, they are usually assigned to a **domain**
- Each domain needs an introduction to explain its theme (features in common to all its patterns)
- Some types of requirements depends on **infrastructure**. They may be added to the pattern through **infrastructure overviews**.

## Requirement pattern groups

- When requirement patterns have **features in common**, a **pattern group** can be created
- Pattern groups differ from domains in the sense the domain patterns share a common **theme**, and the groups have **detailed features** in common.

## Relationships between requirement patterns

- A pattern mught refer to other patterns
- The relationship can be fundamentally a **mention** (**refers to**) or a pattern **extension** (**specialization**)
