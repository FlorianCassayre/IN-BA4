---
title: "Probability and Statistics - Week 2"
author: [Florian Cassayre]
date: 2018-02-27
tags: [proba-stats]
...

## Probability (continuation)

### Probability distribution

A **probability distribution** $P$ assigns a probability to each element of the event space $\mathcal{F}$, with the following properties :

- $A \in \mathcal{F} \implies 0 \leq P(A) \leq 1$
- $P(\Omega) = 1$
- if $\{A_1, A_2, ..., A_n\}$ are pairwise disjoint (every pair of event are mutually exclusive), then $P\left(\bigcup\limits_{i=1}^{n} A_{i}\right) = \sum\limits_{i=1}^{n} P(A_{i})$

Moreover, $P$ is called a **continous set function**.

About $(3)$: the inclusion-exclusion formula has $\binom{n}{1} + \binom{n}{2} + ... + \binom{n}{n} = 2^n - 1$ terms in total (related to the powerset).

### Conditional probability

Let $A, B$ be events of a probability space such that $P(B) > 0$. The **conditional probability** of **$A$ given $B$** is :
$$P(A | B) = \frac{P(A \cap B)}{P(B)}$$

If $P(B) = 0$ we adopt the convention that $P(A \cap B) = 0$.

#### Bayes' theorem

The law of total probability states that :
$$P(A) = \sum\limits_{i=1}^{n} P(A \cap B_i) = \sum\limits_{i=1}^{n} P(A | B_i)P(B_i)$$

Bayes' theorem :
$$P(B_j | A) = \frac{P(A |B_j)P(B_j)}{\sum\limits_{i=1}^{n} P(A | B_i)P(B_i)}$$

#### Prediction decomposition
$$P(A_1 \cap A_2) = P(A_2 | A_1)P(A_1)$$
$$P(A_1 \cap A_2 \cap A_3) = P(A_3 | A_2 \cap A_1)P(A_2 | A_1)P(A_1)$$
$$...$$

### Independence

Intuitively, "$A$ and $B$ are independent" if (and only if) knowing the result of $A$ does not provide any additional information on $B$ (and vice versa).

This can be written as :

$$P(A \cap B) = P(A)P(B)$$
