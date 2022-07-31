---
layout: post
title: "Concurrency Models: Data Parallelism "
date: 2022-03-12 13:01:20 +0300
description: "Model 7: Data Parallelism" # Add post description (optional)
img:  software.jpg # Add image post (optional)(optional)
categories: [concurrent-systems]
icon: blogging.png
---
### Data Parallelism
- Focuses on distributing the data across different nodes, which operate on the data in parallel. It can be applied on regular data structures like arrays and matrices by working on each element in parallel.

#### Data Parallelism vs Task Parallelism
- Data Parallelism means concurrent execution of the same task on each multiple computing core.
- Task Parallelism means concurrent execution of the different task on multiple computing cores.

#### Data parallel programming environments 
- Message Passing Interface: Uses message passing programming interface for parallel computers. It defines library functions to allow users to write portable message passing programs in C, C++ and Fortran
- CUDA and OpenACC: Parallel computing API platforms designed to utilize GPU's computational units for general purpose processing.