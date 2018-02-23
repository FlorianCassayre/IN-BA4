---
title: "Parallelism and Concurrency - Week 1"
author: [Florian Cassayre]
date: 2018-02-21
tags: [parallelism-concurrency]
...

## Parallel computing

Assuming we have parallel hardware, it is a type of computation in which many calculation are done at the same time.

The _only_ reason is speedup.

## Concurrent programming

The goal is to improve either modularity, responsiveness or maintainability. May not necessarily execute multiple tasks at the same time.

## Parallelism on the JVM

- The operating system assigns a **process** to each application. The processes can't share memory.
- Processes are split up in **threads**, which can be started from the same program and do share the same memory while still having a separate program stack.

```Scala
class ExampleThread extends Thread {
  override def run() {
    println("Hello world!")
  }
}

val thread = new ExampleThread() // Instanciate a new thread object
thread.start()                   // Actually starts the thread
thread.join()                    // Wait for thread to complete its execution
```

### Atomicity

An operation is atomic if it appears as if it occurred instantaneously from the point of view of other threads.

### The `synchronized` block

The synchronized block is used to achieve atomicity. Operations on a synchronized object are always done by a single thread at the same time.

Invocations of the `synchronized` block can be nested, but **beware**: they must **always** be performed in the same order or else they can lead to **deadlocks** (a "dead" state in which two threads are competing against each other for a resource).

### Basic `parallel` construct

```Scala
parallel(e1, e2)
```
