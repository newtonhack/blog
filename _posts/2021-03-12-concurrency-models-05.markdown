---
layout: post
title: "Concurrency Models: CSP "
date: 2022-03-12 13:01:20 +0300
description: "Model 5: Communicating Sequential Processes" # Add post description (optional)
img:  software.jpg # Add image post (optional)(optional)
categories: [concurrent-systems]
icon: blogging.png
---
### Communicating Sequential Processes
CSP is a high-level concurrency model (introduced in 1978 by Tony Hoare) that combines the sequential thread (threaded state) abstraction with synchronous message passing communication. The message passing primitive is a blocking queue that blocks both on send and receive, meaning that the concurrent computations perform a rendezvous.

### Channels
- A program using the communicating sequential processes model similarly consists of independent, concurrently executing entities that communicate by sending each other messages. 
- The difference is instead of focusing on the entities sending the messages, CSP focuses on the channels over which they are sent. Channels are first class—instead of each process being tightly coupled to a single mailbox, channels can be independently created, written to, read from, and passed between processes.
- A channel is a thread-safe queue—any task with a reference to a channel can add messages to one end, and any task with a reference to it can remove messages from the other. Unlike actors, where messages are sent to and from specific actors, senders don’t have to know about receivers, or vice versa.
- By default, channels are synchronous (or unbuffered)—writing to a channel blocks until something reads from it



### CSP vs Actors
- Processes in CSP are anonymous, while actors have identities.
CSP uses channels for message passing, whereas actors use mailboxes.
- Actor must only communicate through message delivery, hence making them stateless.
- CSP messages are delivered in the order they were sent.
- The actor model was designed for distributed programs, so it can scale across several machines.
- Actor model is more decoupled than CSP.