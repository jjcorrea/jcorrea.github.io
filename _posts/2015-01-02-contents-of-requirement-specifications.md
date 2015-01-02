---
layout: post
title: Contents of requirement specifications
---

There is not a single right way to **organize requirements specification**, but certain topics recur in most systems and deserve their own sections. The following model is a suggested **structure** for requirements specification.

## Introduction section

### System purpose

- What the system **is for**
- **Who wants it**, and **why**
- **Who will use** it
- what is the **business motivation** behind it?
- Describe the **system itself**, not the project which implements it

### Document purpose

- The **role the document plays**
- Brief and concise explanation
- Identify the **audience**
- State disclaimers

### Requirement format

1. **Requirement ID**: Unique identifier. Should be concise, distinctive and sequential
2. **Definition**: Description, in a free-text format
3. **Priority**: How important the requirement is
4. **Summary** description: Sums up the requirement as briefly as possible

### Glossary

- Relevant items
- Term + Definition

### References

- **Documents** and **sources** used

### Document history

- Details of **each version** of the document

## Context section

### Scope

- **How the system fits on real world** around it
- A local map showing where our territory ends, and that of the neighbors starts
- **Context diagram** is a good starting point

Main kinds of information are:

1. **Components**: All **distinct pieces** that must be in-place and **how they connect to each other**
2. **User roles**: Main **roles** in which people interact with the system. System **actors**
3. **Scope boundary**: What is the system **responsability** and what isn't
4. **Intersystem interfaces**: All interfaces via each component **interacts with other systems** and logical components

### Major assumptions

- Each thing which is **assumed to be true** and that would have a **significant impact** on the system if it were not so

### Major exclusions

- Something the system **does not** do
- Any feature **not planned to be supported**

### Key business entities

- Major system entities around which the system performs a set of activities
- State transition diagram to express it

### Infrastructures

- The underlying set of **capabilities needed** to support one or more requirements

## Functional area sections

### Functional areas

- Top-level section for each logical grouping of functions
- Order sections according to their importance

## Major non-functional capabilities section

- Describe important non-functional aspects of a system

# References

Software requirement patterns - Stephen Withall 



