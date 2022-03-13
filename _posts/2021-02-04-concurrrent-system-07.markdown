---
layout: post
title: "Concurrent Systems: 07 "
date: 2021-03-12 13:01:20 +0300
description: "Model 1: Threads & Locks" # Add post description (optional)
img:  software.jpg # Add image post (optional)(optional)
categories: [concurrent-systems]
icon: blogging.png
---
### Threads & Locks ( Mutual Exclusion and Memory Models )
- *Mutual exclusion*: using locks to ensure that only
one thread can access data at a time to ensure we don't get into *race conditions* and *deadlocks*
- Solution for dealing with sections of code which is trying to make changes to *Shared Mutable State* is to *synchronize* those sections using *locks*.
- These sections are also called to as *mutex, monitor, or critical section*
<br/>

#### Some rules that help us avoid race conditions, deadlock, and issues with memory visibility:
- Synchronize all access to shared variables.
- Both the writing and the reading threads need to use synchronization.
- Acquire multiple locks in a fixed, global order.
- Don’t call alien methods while holding a lock.
- Hold locks for the shortest possible amount of time.