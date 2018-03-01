---
title: "Parallelism and Concurrency - Week 2"
author: [Florian Cassayre]
date: 2018-02-28
tags: [parallelism-concurrency]
...

## Parallelism on collections

Operations like `map` and `filter` are easy to parallelize since they can be split up until a specified threshold on different thread and then their solutions can be trivially combined.

Some other operations like `foldLeft` and `reduce` need a little bit more thinking. The parallelization can only be done at a higher total cost **and** with the assumption that the operation we are doing (= the function being applied) is **associative**: $\forall a, b, c: f(f(a, b), c) = f(a, f(b, c))$.

**Reminder**: commutativity does not imply, nor is implied, by associativity.

The reduction can be performed after the transformation of the collection into a **tree** . See _parallel tree reduction_ for more informations.
