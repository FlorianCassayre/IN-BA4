---
title: "Theory of Computation - Week 2"
author: [Florian Cassayre]
date: 2018-03-01
tags: [theory-computation]
...

## What problems can we solve with finite memory? (continuation)

### Nondeterministic Finite Automaton

A **Nondeterministic Finite Automaton** (**NFA**) is also a 5-tuple $(Q, \Sigma, \delta, q_0, F)$ where all parameters are the same as a DFA except $\delta$:

- $\delta: Q \times (\Sigma \cup \{\epsilon\}) \to \mathcal{P}(Q)$ the transition function, where $\mathcal{P}(Q)$ denotes the power set of $Q$

Furthermore, for some input word $x$:

- $x$ is **accepted** if there exists at least one path that starts at a
starting state and ends at an accept state
- $x$ is **rejected** if no computation path from any start state leads to an accept state

$L(N) \subset \Sigma^\star$ is the set of strings accepted by $N$.

NFA have the following properties:

- Ability to transition to **more than one** state on a symbol
- A state may have **no transition** on a symbol
- Ability to take a step **without** reading any input symbol

**Theorem**: for every NFA $N$, there exist a DFA $M$ such that $L(M) = L(N)$. In other words every NFA can be converted to a DFA.

The **concatenation** operation can be easily built with a NFA.
