---
title: "Probability and Statistics - Week 4"
author: [Florian Cassayre]
date: 2018-03-13
tags: [proba-stats]
...

## Probability (continuation)

### Random variables (continuation)

#### Cumulative distribution function

The **cumulative distribution function** (**CDF**) of a random variable $X$ is:

$$F_X(x) = P(X \leq x), x \in \mathbb{R}$$

$$F_X(x) = \sum\limits_{\{x_i \in D_X,\ x_i \leq x\}} P(X = x_i)$$

The support is $D = \{0, 1\}$.

##### Useful properties

- $P(X > x) = 1 - F_X(x)$
- If $x < y$, $P(x < X \leq y) = F_X(y) - F_X(x)$
- If $X$ is a random variable and $Y = g(X)$ (a transformation),

  $$f_Y(y) = \sum\limits_{\{x: g(x) = y\}}f_X(x)$$

#### Expectation

For a discrete random variable $X$, the **expectation** (or **expected value**) of $X$ is defined as:

$$E(X) = \sum\limits_{x \in D_X} x P(X = x) = \sum\limits_{x \in D_X} x f_X(x)$$

Note that if $E(|X|)$ is not finite then $E(X)$ is **not well defined**. In fact expectations don't have to always exist.

**Expectation of a transformed random variable**: let $X$ be a random variable with PMF $f$ and let $g$ be a real function of $X$:

$$E(g(X)) = \sum\limits_{x \in D_X} g(x)f(x)$$

when $\sum\limits_{x \in D_X} |g(x)|f(x) < \infty$.

##### Useful properties

- $E(\dot\ )$ is a linear operator, namely $E(aX + b) = aE(X) + b$
- If $f(X)$ and $g(X)$ have finite expected values, $E(f(X) + g(X)) = E(f(X)) + E(g(X))$
- If $P(X = b) = 1$, then $E(X) = b$
- If $P(a < X \leq b) = 1$, then $a < E(X) \leq b$
- $E(X)^2 \leq E(X^2)$

#### Moments of a distribution
