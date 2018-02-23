---
title: "Theory of Computation - Week 1"
author: [Florian Cassayre]
date: 2018-02-22
tags: [theory-computation]
...

## What problems can we solve with finite memory?

### Deterministic Finite Automaton

[DFA example](https://upload.wikimedia.org/wikipedia/commons/9/94/DFA_example_multiplies_of_3.svg)

A **Deterministic Finite Automaton** (**DFA**) is a 5-tuple $(Q, \Sigma, \delta, q_0, F)$:

- $Q$ the set of **states**
- $\Sigma$ the **alphabet**
- $\delta: Q \times \Sigma \to Q$ the **transition function**
- $q_0$ the **initial state**
- $F \subset Q$ the set of **accepting states**

$\Sigma^\star$ is the set of all strings composed of symbols from $\Sigma$. It includes the **empty string** $\epsilon$.

$L(M) \subset \Sigma^\star$ is the set of strings **accepted** by $M$.

### Regular languages

$L$ is a **regular language** if there is a DFA machine such that $L = L(M)$. In other words, if there exist a DFA machine $M$ that accepts $L$ then this language is regular.

#### Operations on languages

- **Complement**
  - $\overline{L} := \{w \in \Sigma^\star: w \notin L\}$
- **Union**
  - $L_1 \cup L_2 := \{w \in \Sigma^\star: w \in L_1\ or\ w \in L_2\}$
- **Intersection**
  - $L_1 \cap L_2 := \{w \in \Sigma^\star: w \in L_1\ and\ w \in L_2\}$
- **Concatenation**
  - $L_1 \circ L_2 := \{w \in \Sigma^\star: w = w_1 \circ w_2, w_1 \in L_1\ and\ w_2 \in L_2\}$

***Theorem:*** Let $L_1, L_2$ be a regular languages. Any (finite) combination of the previous stated operations yields another regular language.
