---
layout: post
title: "Concurrency Models: Actors "
date: 2022-03-12 13:01:20 +0300
description: "Model 4: Actors" # Add post description (optional)
img:  software.jpg # Add image post (optional)(optional)
categories: [concurrent-systems]
icon: blogging.png
---
### Actors
- Functional programming avoids the problems associated with shared mutable state by avoiding mutable state. 
- Actor programming, by contrast, retains mutable state but avoids sharing it. 
- An actor is like an object in an object-oriented (OO) program—it encapsulates state and communicates with other actors by exchanging messages. The difference is that actors run concurrently with each other and, unlike OO-style message passing (which is really just calling a method), actors really communicate by sending messages to each other.
- One of the most important features of actor programming is that messages are sent asynchronously. Instead of being sent directly to an actor, they are placed in a mailbox, making actors are decoupled—actors run at their own speed and don’t block when sending messages.


#### Messages & Mailbox
- "let it crash” philosophy, allows actor programs to be fault-tolerant. Since sending & messages are handled async way.
- Mailboxes are Queues, ensuring sequence of causal delivery of messages.

#### Receiving of messages
- An actor typically sits in an infinite loop, waiting for a message to arrive with receive and then processing it.


#### Stateful Actors
- Actors can have state persistence & replication for scale


### Strengths
- Actors have a number of features that make them ideal for solving a wide range of concurrent problems.
- Messaging and Encapsulation
- Fault Tolerance
- Actors’ support for both shared and distributed-memory architectures brings a number of significant advantages
    - it allows an actor program to scale to solve problems of almost any size. We are not limited to problems that fit on a single system.
    - it allows us to address problems where geographical distribution is an intrinsic consideration. Actors are an excellent choice for programs where different elements of the software need to reside in different geograph- ical locations.

### Weakness
- Although a program constructed with actors is easier to debug than one constructed with threads and locks, actors are still susceptible to problems like deadlock plus a few failure modes unique to actors (such as overflowing an actor’s mailbox).
- As with threads and locks, actors provide no direct support for parallelism. Parallel solutions need to be built from concurrent building blocks, raising the specter of nondeterminism. 
- Since actors do not share state and can only communicate through message passing, they are not a suitable choice if you need fine-grained parallelism.