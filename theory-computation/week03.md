---
title: "Theory of Computation - Week 3"
author: [Florian Cassayre]
date: 2018-03-08
tags: [theory-computation]
...

## What problems can we solve with finite memory? (continuation)

### Is every language regular

#### What DFAs/NFAs can do

- **Pattern matching** (for instance find substrings)
- Checking **parity**, **divisibility**, **modulo counting**
- Skipping prefixes/suffixes, more generally **regular expressions**
- **Closure** under complements, **unions**, **intersections**, **concatenation**

#### What DFAs/NFAs can't do

The following language - for example, is not regular:

$L = \{0^n1^n\ |\ n \geq 0\} = \{\epsilon, 01, 0011, 000111, \dots\}$

##### Proof

One want to prove that a language is not regular is to use a proof by contradiction.

- Suppose that $L$ is recognized by some DFA with $p$ states ($p$ being a fixed number)
- Consider what happens when the input is long enough, in our case $0^{p+1}$
- Thus, for two strings $0^i, 0^j, i \neq j$ we have to end up in the same state because $p$ is finite
- Since $0^i1^i$ is accepted, $0^j1^i$ is also accepted; which contradicts our initial assumption ("$L$ is regular")
- Hence $L$ is **not regular**

##### The pumping lemma

If $L$ is a regular language, then there is a number $p$ (the pumping length) such that, for every string $s$ in $A$ of length at least $p$, there exists a division of $s$ into three pieces, $s = xyz$ such that:

1.  $\forall i \geq 0, xy^iz \in A$
2. $|y| \geq 1$
3. $|xy| \leq p$

##### Applications of the pumping lemma

Note that **not every** string leads to a contradiction! (have to choose it carefully)

Moreover, $B \subset C$ and $B$ is non-regular **does not imply** $C$ is non-regular.

- $B = \{ww\ |\ w \in \{0, 1\}^\star\}$

  - Assume $B$ is regular, let $p$ be the pumping length
  - Pick **$s = 0^p1^p0^p1^p \in F$**
  - Using the pumping lemma, $|xy| \leq p$ and $|y| \geq 1$; thus **$y = 0^k$** for some **$k > 0$**
  - According to the pumping lemma, **$xy^2z \in F$**
  - **$xy^2z = 0^{p+k}1^p0^p1^p \notin F$**

- $C = \{0^m1^n\ |\ m > n\}$

  - Assume $C$ is regular, let $p$ be the pumping length
  - Pick **$s = 0^{p+1}1^p \in F$**
  - Using the pumping lemma, $|xy| \leq p$ and $|y| \geq 1$; thus **$y = 0^k$** for some **$k > 0$**
  - According to the pumping lemma, **$xy^0z = xz \in F$**
  - **$xz = 0^{p+1-k}1^p$** and since **$p + 1 - k \leq p$**, **C $\notin F$**

- $D = \{w\ |\ w\ has\ an\ equal\ number\ of\ 0's\ and\ 1's\}$

  - We'll reuse a proven result
  - Assume $D$ is regular
  - We know that an intersection of two regular languages is also regular
  - Hence $D \cap \{0^\star1^\star\} = \{0^n1^n\}$ has to be regular (but we proved it's not)
