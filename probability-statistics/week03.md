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

#### Distributions

We write $X \sim Y(\dots)$ as "$X$ has the distribution $Y$".

##### Binomial distribution

A **binomial** random variable $X$ with parameters $n$ and $p$ has PMF:

$f_X(x) = \binom{n}{x} p^x(1-p)^{n-x},\ x = 0, 1, \dots, n,\ n \in \mathbb{N}, 0 \leq p \leq 1$

We write $X \sim B(n, p)$ and call $n$ the **denominator** (the number of successes) and $p$ the **success probability**. The mass function corresponds to the probability of obtaining (exactly) $x$ successes from $n$ trials of experiments of probability $p$.

![](https://upload.wikimedia.org/wikipedia/commons/4/4a/Binomial_Distribution.PNG)

- $R \sim B(n = 20, p = 0.8)$
- $G \sim B(n = 20, p = 0.5)$
- $B \sim B(n = 20, p = 0.1)$

##### Geometric distribution

A **geometric** random variable $X$ has PMF:

$f_X(x) = p(1 - 1)^{x-1},\ x = 1, 2, \dots,\ 0 \leq p \leq 1$

We write $X \sim Geom(p)$ and call $p$ the **success probability**.
The mass function corresponds to the probability of getting the first success after (exactly) $x$ experiments of probability $p$.

It is _memoryless_, the events are independent and have equal probability.

![](https://upload.wikimedia.org/wikipedia/commons/f/ff/Geometrische_Verteilung.PNG)

- $R \sim Geom(p = 0.8)$
- $G \sim Geom(p = 0.5)$
- $B \sim Geom(p = 0.2)$

##### Negative binomial distribution

A **negative binomial** random variable $X$ with parameters $n$ and $p$ has PMF:

$f_X(x) = \binom{x-1}{n-1} p^n(1-p)^{x-n},\ x = n, n + 1, n + 2, \dots, \ n \in \mathbb{N}, 0 \leq p \leq 1$

We write $X \sim NegBin(n, p)$. When $n = 1$, $X \sim Geom(p)$.
The mass function corresponds to the probability of obtaining $x$ successes after $x$ trials of experiments of probability $p$. It can be seen as a generalization of the geometric distribution.

![](https://upload.wikimedia.org/wikipedia/commons/2/2c/Negativ_Binomial_Distribution.PNG)

- $R \sim NegBin(n = 10, p = 0.8)$
- $G \sim NegBin(n = 10, p = 0.5)$
- $B \sim NegBin(n = 10, p = 0.2)$

##### Hypergeometric distribution

A **hypergeometric** random variable $X$ with parameters $w$, $b$ and $n$ has PMF:

$f_X(x) = \frac{\binom{w}{x}\binom{b}{m-x}}{\binom{w+b}{m}}$, $x = max(0, m - b), \dots, min(w, m)$

We write $X \sim HyperGeom(w, b, n)$. From a urn of $w$ white balls and $b$ black balls, it corresponds to the probability of drawing $x$ white balls in a sample of $m$ balls.


![](https://upload.wikimedia.org/wikipedia/commons/5/59/Hypergeometrische_Verteilung.PNG)

- $R \sim HyperGeom(w = 20, b = 60, n = 20)$
- $G \sim HyperGeom(w = 50, b = 60, n = 10)$
- $B \sim HyperGeom(w = 20, b = 30, n = 10)$

##### Discrete uniform distribution

A **discrete uniform** random variable $X$ with parameters $a$ and $b$ has PMF:

$f_X(x) = \frac{1}{b - a + 1}$, $x = a, a + 1, \dots, b$, $a < b$, $a, b \in \mathbb{Z}$

We write $U \sim DU(a, b)$. Basically just a generalization of a die throw (which would be $DU(1, 6)$). Note that $f_X(x)$ is independent of $x$.

##### Poisson distribution

A **Poisson** random variable $X$ with parameters $\lambda$ has PMF:

$f_X(x) = \frac{\lambda^x}{x!}e^{-\lambda}$, $x = 0, 1, \dots$, $\lambda > 0$

We write $X \sim Pois(\lambda)$. Used to study the number of successes in a fixed time interval.

![](https://upload.wikimedia.org/wikipedia/commons/5/59/Poisson-Verteilung.PNG)

- $R \sim Pois(\lambda = 10)$
- $G \sim Pois(\lambda = 5)$
- $B \sim Pois(\lambda = 1)$
