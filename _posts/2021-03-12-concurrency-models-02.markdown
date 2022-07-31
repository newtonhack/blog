---
layout: post
title: "Concurrency Models: Atomics "
date: 2021-03-12 13:01:20 +0300
description: "Model 2: Atomics Condition Variables & Timeouts" # Add post description (optional)
img:  software.jpg # Add image post (optional)(optional)
categories: [concurrent-systems]
icon: blogging.png
---
### Timeouts
- Timeouts of acquisition of Locks
- Allows us to time out while trying to acquire a lock, this can help avoid permanent deadlock state.

### Condition Variables
- Concurrent programming often involves waiting for something to happen.
Example: we need to wait for a queue to become nonempty before removing
an element from it. Or we need to wait for space to be available in a buffer
before adding something to it. This type of situation is what condition variables
are designed to address.
- A condition variable is associated with a lock, and a thread must hold that
lock before being able to wait on the condition. Once it holds the lock, it
checks to see if the condition that it’s interested in is already true. If it is,
then it continues with whatever it wants to do and unlocks the lock

### Atomics
- Atomic variables are the foundation of non-blocking, lock-free algorithms, which achieve synchronization without locks or blocking. 

#### Overcome the limitations of intrinsic locks so that our threads can do the following:
- Be interrupted while trying to acquire a lock
- Time out while acquiring a lock
- Acquire and release locks in any order
- Use condition variables to wait for arbitrary conditions to become true
- Avoid locks entirely by using atomic variables


### Let framework deals with complexities
Mutli-Threading Frameworks contains a collection of general-purpose, high-performance, and thoroughly debugged concurrent data structures and utilities.

- **Thread-Creation Redux**
    - Use thread pools instead of creating threads directly
    - Thread pool like framework
    - Example: Java Executor Framework
- **Copy-On-Write Data-structures**
    - Create a Copy on Write thereby share of mutable state is none.
    - Creating simpler and more efficient listener-management code with `CopyOnWriteArrayList`
- Allowing producers and consumers to communicate efficiently with `ArrayBlockingQueue`
- Supporting highly concurrent access to a map with `ConcurrentHashMap`