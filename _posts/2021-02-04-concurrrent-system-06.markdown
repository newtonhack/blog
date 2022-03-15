---
layout: post
title: "Concurrent Systems: 06 "
date: 2021-03-12 13:01:20 +0300
description: Types of Concurrency Models # Add post description (optional)
img:  software.jpg # Add image post (optional)(optional)
categories: [concurrent-systems]
icon: blogging.png
---
### Concurrency vs Parallelism
- **Concurrency** is about dealing with lots of things at once
- **Parallelism** is about doing lots of things at once

### A Big Question
What is the bottle neck between **Parallel-Multi-Core-Fast &** need to your **code to go Blocking**?
>Answer: Shared Mutable State

### Why so many concurrency models
Concurrency Models help eliminate complexies which rises when one have to choose to move the code execution in concurrent mode. They try to imply mechanisms to somehow manage/eliminate *Shared Mutable State*.

<br/>

One can achieve concurrency without a worry if they can 
- **Eliminate Shared Mutable State** \
OR 
- **Make the data share transactional**. (ACID Properties) 

<br/>

### Features of Concurrency Models
All the models which exists till date sort of tries to eliminate one of (shared/mutable/state) or make things transactional. 

### Types of Concurrency Models
- Threads & Locks
- Atomics Condition Variables & Timeouts (beyond locks)
- Functional Programming
- Actors
- Communicating Sequential Process
- Software Transaction Memory
- Data Prallelism
- Lambda Architecture
- Event-Driven Architecture