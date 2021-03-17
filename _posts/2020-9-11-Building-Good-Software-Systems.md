---
layout: post
tags: notes
excerpt_separator: <!--more-->
title: Building Good Software Systems
---

What are the properties of *good* software?

 - 3C's: **Correct, Comprehensible, Changeable**

How do we build software... that works... and be convinced that it is correct?

<!--more-->

#### Critical Software
- *Important Systems:* Operating systems, network stacks, medical devices, etc...
- *Programming Languages and Tools:* Static type systems, compilers...

- Reasoning about **software correctness:**
  - Logic
  - Reasoning about *individual programs*
  - Reasoning about *whole systems* (and its tools)

### Static Analysis
- What do we know about the program *before* we run it? Is it correct?

- A compiler carries out some static analyses

#### **Static type checking (Type safety):** `x = y;`
- The compiler verifies that `x` and `y` are compatible

  - Major source of bugs in software

  - However, compiler analysis may be incorrect!

- Java and other high-level languages allow us to **define new types** and have greater checks for type safety

- **Dynamic checking:** Verification of correctness *at runtime* (bugs detected during program execution)

  - Java supports dynamic verification because programs run on the Java Virtual Machine


- **No checking:** Assembly, for example, requires great programmer care -- no support for verifying even basic properties

### Establishing Correctness
#### A History

- How do we know something is true? *We prove it.*

- How do we know we have a proof? *Define what it means to be a proof.*
  - We need a language and notations to express and formalize arithmetic: Gottlob Frege
  - Frege's language was inconsistent: Russell's Paradox
  - Godel's incompleteness theorems: "This statement is not provable"


  - Types <-> Propositions
  - Programs <-> Proofs
  - Computation <-> Simplification

#### Building Reliable Software

##### Approaches to Software Reliability

- *Less formal:* Lightweight, inexpensive, may miss problems
  - **Social, Methodological**


- *More formal:* Eliminates problems with certainty
  - **Technological, Mathematical**
  - With large projects, tools are still getting developed


- Not a "trade-off": All methods should be used!

#### What we will focus on
- Specifications and testing (and exceptions, to boot)
- Better use of types
- Constructing robust types
- Concise idioms (stream processing)
- Handling concurrency (some simple network operations)
- A little bit of grammar and parsing
