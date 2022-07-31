---
layout: post
title: "Concurrency Models: Functional Programming "
date: 2021-03-12 13:01:20 +0300
description: "Model 3: Functional Programming" # Add post description (optional)
img:  software.jpg # Add image post (optional)(optional)
categories: [concurrent-systems]
icon: blogging.png
---
### Functional Programming
- It consists of a series of statements that change global state when executed, a *functional program* models computation as the evaluation of expressions. These expressions are built from pure mathematical functions that are both first-class (can be manipulated like any other value) and side effect–free. 

#### Rationale
In this model, we try to circumvent to avoid *shared mutable state*. Immutable structures  can be accessed by multiple threads without any kind of locking. So focus is on 
- **Programming without mutable State** \
    - Functional programming makes concurrency easier and safer by eliminating shared mutable state.
    - Lazy evalution of functions, and its compositions

- **Functional Parallelism** \
    - With elimination of *shared mutable state*, functions can be executed in parallel, memoized to increase performance by Runtime.
    - Divide & Conquer to combine and reduce. Fork and Join

- **Functional Concurrency**
    - Same Structure, Different Evaluation Order
    - Referential Transparency: \
    Pure functions are referentially transparent—anywhere an invocation of the function appears, we can replace it with its result without changing the behavior of the program
    - Futures: \
    A future takes a body of code and executes it in another thread. Its return value is a future object:
    - Promise: \
    A promise is very similar to a future in that it’s a value that’s realized asynchronously and accessed with some deref mechanism (`await`), which will block until it’s realized. The difference is that creating a promise does not cause any code to run—instead its value is set with deliver.


#### Monads & Monoids
Monads and Monoids to allow its type system to accurately encode restrictions on where particular functions and values can be used and to keep track of side effects while remaining functional.
A monad is based on a simple symmetry — A way to wrap a value into a context, and a way to unwrap the value from the context. Example: Java `Option<Type>` or `Result<Type>` pattern \
**Difference between Monad & Monoid?**
> Monoids encapsulate a binary operation.



### Strengths
- The primary benefit of functional programming is confidence, confidence that your program does what you think it does. Once you’ve got into thinking functionally (which can take a while, especially if you have years of experience with imperative programming), functional programs tend to be simpler, easier to reason about, and easier to test than their imperative equivalents.
- Once you have a working functional solution, referential transparency allows you to parallelize it, or operate in a concurrent environment, with very little effort. 
- Because functional code eliminates mutable state, the majority of the concurrency bugs that can show up in traditional threads and locks–based programs are impossible.

### Weakness
- #todo (Parked for more details)