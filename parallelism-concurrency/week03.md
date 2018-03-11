---
title: "Parallelism and Concurrency - Week 2"
author: [Florian Cassayre]
date: 2018-02-28
tags: [parallelism-concurrency]
...

## Parallel collections

In Scala most operations on collections can become data-parallel. One can do so by calling the `.par` construct:

```Scala
collection.par
```

### The `fold` operation

However operations like `foldLeft` cannot be parallelized due to their intrinsic nature. However, functions like `fold` - which can form reductions trees are parallelizable.

`fold[A](z: A)(f: (A, A) => A)`

#### Example

The following function:

```Scala
def sum(xs: Array[Int]): Int = {
  xs.par.foldLeft(0)(_ + _)
}
```

...can also be written as:

```Scala
def sum(xs: Array[Int]): Int = {
  xs.par.fold(0)(_ + _)
}
```

...which gets correctly processed in parallel.

#### Preconditions

In order for the `fold` to yield the correct result, the following equalities must hold for the reduction function $f$, the elements to be reduced $a$, $b$ and $c$, and the initial accumulator $z$:

```Scala
f(a, f(b, c)) == f(f(a, b), c) // Associativity
f(z, a) == f(a, z) == a        // Identity
```

### The `aggregate` operation

The `fold` operation has some limits due to its signature (the reduction must occur on elements of the same type).

`aggregate[B](z: B)(f: (B, A) => B, g: (B, B) => B)`
