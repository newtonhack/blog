---
layout: post
title: "Concurrency Models: STM "
date: 2022-03-12 13:01:20 +0300
description: "Model 6: Software Transaction Memory" # Add post description (optional)
img:  software.jpg # Add image post (optional)(optional)
categories: [concurrent-systems]
icon: blogging.png
---
### Software Transaction Memory
- Software transactional memory (STM) is a technique for simplifying concurrent programming by allowing multiple state-changing operations to be grouped together and performed as a single atomic operation.
- A concurrency control mechanism analogous to database transactions for controlling access to shared memory in concurrent computing.(**Compare & Swap instead of locks**) It is an alternative to lock-based synchronization.
- STM provides applications programmers with an alternative to mutual-exclusion locks which avoids many of the latter’s pitfalls, including risk of deadlock, unnecessary serialization, and priority inversion

#### Example Datastructures
- Structures in Clojure & Haskell

