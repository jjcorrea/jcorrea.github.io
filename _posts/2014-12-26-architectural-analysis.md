---
layout: post
title: Architectural analysis
---

There are many different approaches for analyzing software systems, generally consisted of the following activities:

- Development of **architectural models**: The data is collected during the requirements gathering to be analyzed and incorporated to the architectural model.
- **Enhancement and synthesis** of a solution: Enhances the information described on the initial architectural model.
- **Solution** analysis: Analysis of the solution performed in terms of architectural model.

Notice the architectural model as an initial **draft** of the (under development) system architecture. The architectural models are defined from a set of *architectural requirements* on an iterative process.

## Software architecture properties

Apart from the [architectural requirements](http://jjcorrea.github.io/2014/11/30/architectural-requirements/) which has been showed on a previous post, an architecture also presents some properties which can be seen as intrinsic to it, which are: **Efficiency**, **integrity** and **flexibility**.

### Efficiency

The amount of computational resources required by a system to perform its activities indicates its efficiency. The resources can be seen in terms of **storage** and **processment**. 

One of the main requirements related to efficiency is **performance**. 

### Integrity

The architectural integrity is measured in terms of the project **unification in different levels**. The software architecture describes the system organization in a high level, and targets the objects unification, in other words it serves as a reference to the project.

### Flexibility

The efford required to **change** a software system.

## SAAM - Software architecture analysis method

Initially designed for supporting software architects to **compare architectural solutions** (Kazman, 1994). Initial targets:

- Define a set of **usage scenarios** which are important on the *domain*, to the system main stakeholders.
- **Domain functional partitioning**, followed by linking the existing functions in a partition to usage scenarios.
- Use the functional partition and the scenarios to **analyze the proposed architectures**.

All the **candidate architectures** receive an **score** per usage scenario, and in the end, a global score.

SAAM consists on the following 5 interdependent steps:

1. **Scenario** development: Develop scenarios of tasks that illustrate the sorts of activities which the system must support. Those will cover the *non-functional requirements*.
2. Architectural description: Describe the **components** and **connections** used on the architecture specification.
3. Scenario evaluation: Determine whether the candidate architecture directly supports the tasks associated to the scenario, or if any change is necessary.
4. Scenario interaction: Indicates the tasks that the components are associated to. **SOC**. **Isolation**.
5. Scenario and interaction **evaluation**: The most subjective step on the analysis, the outcome is a global score composed of each scenario and interaction supported by each architecture.

## ATAM - Architecture tradeoff analysis method

Indicates the **consequences of architectural decisions** related to the quality requirements of a system (Kazman, 1999). Evaluates the **architectural solution**, identifying potential **risks** associated to it.

The fundamental aspects under which the method was developed:

1. Quality attributes characterization
2. Scenario analysis to obtain a consensus between system stakeholders.
3. Architectural decision analysis, based on [ABAS](http://resources.sei.cmu.edu/library/asset-view.cfm?assetid=13505) (attribute-based architectural style) which illustrate how architectural decisions can affect quality attributes.

The ATAM method comprehends nine steps which are distributed on four phases as follows:

### 1st step: Presentation

#### 1. ATAM method presentation

Describe the method to the sistem's stakeholders. The set of stakeholders includes: software architects, users / clients, managers, testing & QA team.

#### 2. Company targets presentation

The project manager describes which are the business targets which are triggering the development efford, and consequently which are the main architectural requirements (as security level, availability, etc).

#### 3. Architecture presentation

The architect presents the proposed architecture, focusing on how the business targets will be fulfilled.

### 2nd step: Investigation and analysis

#### 4. Architectural approaches identification

The architects identifies the possible architectural approaches, but doesn't analyze them.

#### 5. Quality attributes utility tree generation

The quality attributes are clarified, and specified using scenarios, including priorities where they exist.

#### 6. Architectural approach analysis (1)

The architectural approaches which satisfies the quality attributes mapped on step 5 are analyzed.

### 3rd step: Test

#### 7. Analysis, discussion and scenario priorization

All the stakeholders participate of a voting process giving priorities to the set of scenarios specified on step 5.

#### 8. Architectural approach analysis (2)

The architectural approach analysis performed on step 6 is now repeated, but specifically for scenarios which derivates from step 7.

### 4th step: Report

#### 9. Results presentation

The ATAM work team presents the results obtained based on the information collected though the method. This information includes scenarios, architectural styles, utility tree, quality attributes, risks. A report is elaborated detailing the results and presenting the strategy to be taken.

### Highlights

- There are **architectural properties** instrinsic to the system structure
- These properties, plus the architectural requirements (non-functional and project attributes) are used as the base of the **architectural analysis**
- **SAAM (Software architecture analysis method)**: method to compare architectural solutions
- **ATAM (Architecture tradeoff analysis method)**: evaluates the risks and consequences of architectural decisions.



