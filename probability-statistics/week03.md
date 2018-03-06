---
title: "Probability and Statistics - Week 3"
author: [Florian Cassayre]
date: 2018-03-06
tags: [proba-stats]
...

## Probability (continuation)

### Random variables

 Let $(\Omega, \mathcal{F}, P)$ be a probability space. A **random variable** $X: \Omega \mapsto \mathbb{R}$ is a function from the sample space $\Omega$ taking values in the real numbers $\mathbb{R}$.

The set of values taken by $X$ is called the **support** $D_X$. If $D_X$ is countable, then $X$ is a **discrete random variable**.

#### Bernoulli random variables

A random variable that takes only the values $0$ and $1$ is called an **indicator variable** $I_n$, or a **Bernoulli random variable**, or a **Bernoulli trial**.

#### Probability mass function

The **probability mass function** (**PMF**) of a random variable $X$ is:

$f_X(x) = P(X = x) = P(A_x), x \in \mathbb{R}$

- If $x \in D_X, f_X(x) \geq 0$
- The total probability is $1$

A **binomial** random variable $X$ has PMF:

$f(x) = \binom{n}{x} p^x(1-p)^{n-x},\ x = 0, 1, \dots, n,\ n \in \mathbb{N}, 0 \leq p \leq 1$

We write $X \sim B(n, p)$.

#### Geometric distribution

A **geometric** random variable $X$ has PMF:

$F_X(x) = p(1 - 1)^{x-1},\ x = 1, 2, \dots,\ 0 \leq p \leq 1$

We write $X \sim Geom(p)$ and call $p$ the **success probability**.
It is _memoryless_, the events are independent and have equal probability.
