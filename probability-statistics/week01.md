---
title: "Probability and Statistics - Week 1"
author: [Florian Cassayre]
date: 2018-02-20
tags: [proba-stats]
...

## Sets

### Notions

A set is an **unordered** collection of objects $x_{1}, x_{2}, ..., x_{n}$ is written as $\left\{x_{1}, x_{2}, ..., x_{n}\right\}$.

An **ordered** set is written as $\left( x_{1}, x_{2}, ..., x_{n}\right)$.

The collection of all possible objects in a given context is called the **universe** noted $\Omega$.

The **empty set** is noted $\emptyset$.

If $\forall x \in A$ implies $x \in B$ then $A$ is a **subset** of $B$, namely $A \subset B$.

The **cardinality** of a finite set is its number of elements, noted $\left|{A}\right|$.

### Operations

- The **complement** $A^c$
- The **union** $A \cup B$
- The **intersection** $A \cap B$
- The **difference** $A \setminus B$
- The **symmetric difference** $A \bigtriangleup B = \left(A \cup B\right) \setminus \left(A \cap B\right)$

### Partitions

A **partition** of a universe is a (possibly infinite) collection of non empty subsets $A_1, A_2, ..., A_n$ of this universe such that :

- The subsets are **exhaustive**, $\bigcup\limits_{i=1}^{n} A_{i} = \Omega$
- The subsets are **disjoint**, $\forall i \neq j: A_i \cap A_j = \emptyset$

### Cartesian product

The **cartesian product** of two sets is the set of ordered pairs, namely $A \times B = \left\{{\left(a, b\right): a \in A, b \in B}\right\}$.

## Combinatorics

### Permutations

_Ordered selection_

Given $n$ distinct objects, the number of permutations without repetition of $r$ objects is: $\frac{n!}{(n-r)!}$

Given $n = \sum\limits_{i=1}^r n_i$ objects of $r$ different types, where $n_i$ is the number of object of type $i$ that are indistinguishable from one another, the number of permutations without repetitions of $n$ objects is: $\frac{n!}{n_1!\ n_2!\ ...\ n_r!}$

### Combinations

_Non ordered selection_

Given $n$ distinct objects, the number of way to choose $r$ objects without repetition is: $\binom{n}{r} = \frac{n}{r!(n-r)!}$

The number of ways of distributing $n = \sum\limits_{i=1}^r n_i$ object into $r$ distinct groups of size $n_1, n_2, ..., n_r$, is: $\frac{n!}{n_1!\ n_2!\ ...\ n_r!}$

### Other properties

_Refer to book for a more exhaustive list_

$$\binom{n}{r} = \binom{n}{n - r}$$

$$\binom{n + 1}{r} = \binom{n}{r - 1} + \binom{n}{r}$$

## Probability

### Probability space

Each random experiment has an associated probability space $(\Omega, \mathcal{F}, P)$:

- The **sample space** $\Omega$, all the possible outcomes
- The **event space** $\mathcal{F}$, a collection of subsets of $\Omega$ called the **events**
- The **probability distribution** $P$, a function $\mathcal{F} \to [0, 1]$

The event space $\mathcal{F}$ is a set of the subsets of $\Omega$ such that:

- $\mathcal{F}$ is non empty
- If $A \in \mathcal{F}$ then $A^c \in \mathcal{F}$
- If $\{A_1, A_2, ..., A_n\}$ are elements of $\mathcal{F}$ then $\left(\bigcup\limits_{i=1}^{n} A_{i}\right) \in \mathcal{F}$

The biggest event space for a given _countable universe_ is the power set (the set of _all_ subsets).
