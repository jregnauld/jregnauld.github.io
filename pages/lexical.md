---
layout: page
title: Because you need to know your stuffs
permalink: /lexical/
show_meta: true
# imagefeature path is relative to images/ directory.
imagefeature: foo.png
published: true
description: "List of things that you need to know as iOS Developer"
category: views
comments: false
mathjax: false
noindex: false
sitemap:
    priority: 0.7
    changefreq: 'monthly'
    lastmod: 2016-02-13
# tags will be used as html meta keywords.
tags:
  - "foo boo"
  - "city tx"
---
While I studied, I did a lot of research to re-memorize things and to dig in more about others things.

This page contains my research as notes and ordered by letters.

Furthermore you often know your stuff, but you don't find word to explain it, maybe it should help.

The idea is to keep every note as short as possible.

# A
-------

### AUTORELEASE POOL

# B
-------

### BLOCKS

It's technically a C-level feature and therefore can be used in C, C++, Objective-C and Objective-C++.

Blocks are similar to a function, but is defined inline to another function and shares the scope of that within which it is defined.

A block is an object, because the first variable within the region of memory that a block is defined in is a pointer to a Class object(isa pointer).

* Blocks are created on the stack

* Blocks can be copied to the heap

* Blocks have their own private const copies of stack variables (and pointers)

* Mutable stack variables and pointers must be declared with the __block keyword


#### LINKS
[Effective Objective-C 2.0: 52 Specific Ways to Improve Your iOS and OS X Programs](https://www.amazon.com/Effective-Objective-C-2-0-Specific-Development/dp/0321917014)

[Zen and the Art of the Objective-C Craftsmanship](https://github.com/objc-zen/objc-zen-book#blocks)

# C
-------

### CLANG

### CONTRAVARIANCE

### COVARIANCE

### CURRYING

# D
-------

### DELEGATE
A delegate allows one object to send messages to another object when an event happens.

* It's a one to one relationship between objects.

* The delegate implements a set of methods with void return type.

* Use weak for delegate to avoid memory leak and retain cycle.

# F
-------

### FUNCTOR


# G
-------

###GCC


### GCD: GRAND CENTRAL DISPATCH
Technology to optimize application support for systems with multi-core processors and other symmetric multiprocessing systems.

* Implementation of task parallelism based on the thread pool pattern
* Move the management of the thread pool out of the hands of the developer and closer to the operating system.

#### Advantages

* Eliminate work on your part.

* Reduces the memory penalty your application pays for storing thread stacks in the application's memory space.

* Eliminates the code needed to create and configure your threads

* Eliminates the code needed to manage and schedule work on threads.

* Simplifies the code you have to write

#### LINKS
[Grand central dispatch on wikipedia](https://en.wikipedia.org/wiki/Grand_Central_Dispatch)

[Grand Central Dispatch vs NSThreads?](http://stackoverflow.com/questions/9238135/grand-central-dispatch-vs-nsthreads)


# H
-------

### HEAP

The heap is where all Objective-C objects live. It is a giant heaping mess of objects. You use pointers to keep track of where those objects are stored in the heap.
When you send the alloc message to a class, a chunk of memory is allocated from the heap. This chunk is your object, and it includes space for the object’s instance variables.

* It is important to destroy objects that are no longer needed to free up heap memory so that it can be reused to create new objects

* The heap is typically allocated at application startup by the runtime, and is reclaimed when the application (technically process) exits.

* The size of the heap is set on application startup, but can grow as space is needed (the allocator requests more memory from the operating system).

[https://vikashazrati.files.wordpress.com/2007/10/stacknheap.png]

[iOS Programming: The Big Nerd Ranch Guide 5th Edition](https://www.bignerdranch.com/we-write/ios-programming/)
[What is the difference between the stack and the heap?](https://www.quora.com/What-is-the-difference-between-the-stack-and-the-heap)
[What and where are the stack and heap?](http://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap)
[Stack and Heap](https://vikashazrati.wordpress.com/2007/10/01/quicktip-java-basics-stack-and-heap/)
#L
-------

### LLDB

# M
-------

### MONADS


# S
-------

### STACK

# W
-------

### WEAK
Weak is used to create a weak reference (pointer) to an object which does not participate in keeping that object alive.

#### WHEN
Where you want to keep a reference to an object, but don't want to keep that object in memory beyond its normal lifetime.

* Example: weak reference to self used in block can prevent retain cycle while ensuring that your program doesn't crash if the block is called after self is deallocated.

#### HOW
On dealloc, on object containing weak points will remove them from the internal mapping table that their target back to them.

Every class maintains a set of addresses of weak points that are pointing on it and when its dealloc is called its sets them all to zero.

* No tracking involved: fast

* ARC just inserts the code to add a pointer to that every time the object is assigned to a new weak reference.

#### LINKS
[Zeroing Weak References](https://www.mikeash.com/pyblog/friday-qa-2010-07-16-zeroing-weak-references-in-objective-c.html)

[How does the ARC's zeroing weak pointer behavior implemented?](http://stackoverflow.com/questions/8859666/how-does-the-arcs-zeroing-weak-pointer-behavior-implemented)
