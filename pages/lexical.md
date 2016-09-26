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
Clang is a compiler front end for the programming languages C, C++, Objective-C, Objective-C++. It uses LLVM as its back end and has been part of the LLVM release cycle.

Clang can parse and analyze any source code in the C language family (C, C++, ObjectiveC, etc…) and has a wonderful modular design that makes it easy to use.

The Clang Static Analyzer is a tool that automatically finds bugs in your code.

The Clang frontend provides more accurate error messages than GCC.

#### HOW

*  Clang will run the Preprocessor (expanding all macros) and parse your source code into an Abstract Syntax Tree (AST)

* If you need to analyze or modify code at the source level, Clang is better than LLVM. Doing analysis with LLVM means you must use LLVM’s internal representation of the code, which is similar to assembly.

#### LINKS
[Clang wikipedia](https://en.wikipedia.org/wiki/Clang)

[Clang introduction](https://kevinaboos.wordpress.com/2013/07/23/clang-tutorial-part-i-introduction/)

[LLVM vs. GCC for iOS development](http://stackoverflow.com/questions/4589335/llvm-vs-gcc-for-ios-development)

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

* A Functor is any type that defines how map applies to it

* Example: map magically applies this function, because Optional is a Functor. It specifies how map applies to Some S  and None S

```
Optional.Some(2).map { $0 + 3 }
```

* A functor is a type that implements map.

* Chain transformations of contained value

* It allows us to get a new container, where the value(s) wrapped inside are transformed according to a function

#### LINKS
[Using Monads and Other Functional Paradigms in Practice](https://realm.io/news/slug-raheel-ahmad-using-monads-functional-paradigms-in-practice-functors-patterns-swift/)

[Swift Functors, Applicatives, and Monads in Pictures](http://www.mokacoding.com/blog/functor-applicative-monads-in-pictures/)

[Functor and Monad in Swift ](http://www.javiersoto.me/post/106875422394)

[What The Heck Is A Monad](http://khanlou.com/2015/09/what-the-heck-is-a-monad/)

# G
-------

### GCC

The GNU Compiler Collection (GCC) is a compiler system produced by the GNU Project supporting various programming languages. It's not use anymore for iOS Project.

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

* The heap is typically allocated at application startup by the runtime, and is reclaimed when the application exits.

* The size of the heap is set on application startup, but can grow as space is needed (the allocator requests more memory from the operating system).

* You would use the heap if you don't know exactly how much data you will need at runtime or if you need to allocate a lot of data.

![](https://vikashazrati.files.wordpress.com/2007/10/stacknheap.png?raw=true)

#### LINKS
[iOS Programming: The Big Nerd Ranch Guide 5th Edition](https://www.bignerdranch.com/we-write/ios-programming/)

[What is the difference between the stack and the heap?](https://www.quora.com/What-is-the-difference-between-the-stack-and-the-heap)

[What and where are the stack and heap?](http://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap)

[Stack and Heap](https://vikashazrati.wordpress.com/2007/10/01/quicktip-java-basics-stack-and-heap/)

#L
-------

### LLDB
LLDB is a high-performance debugger.
LLDB is the default debugger in Xcode on Mac OS X and supports debugging C, Objective-C and C++ on the desktop and iOS devices and simulator.

#### LINKS
[The LLDB Debugger](http://lldb.llvm.org/)

### LLVM
The LLVM(Low Level Virtual Machine) compiler infrastructure project  is a "collection of modular and reusable compiler and toolchain technologies" used to develop compiler front ends and back ends.
In Xcode, the LLVM compiler uses the Clang front end to parse source code and turn it into an interim format. Then the LLVM code generation layer (back end) turns that interim format into final machine code

#### LINKS
[LLVM Wikipedia](https://en.wikipedia.org/wiki/LLVM)

[Apple doc](https://developer.apple.com/library/content/documentation/CompilerTools/Conceptual/LLVMCompilerOverview/index.html)


# M
-------

### MONADS

* A monad is a type of Functor

* A monad is a type that implements flatMap.

* Chain operations on contained value

![](http://adit.io/imgs/functors/recap.png?raw=true)

* functors: you apply a function to a wrapped value using map.

* applicatives: you apply a wrapped function to a wrapped value using apply, if defined.

* monads: you apply a function that returns a wrapped value, to a wrapped value using flatMap.

#### LINKS
[Using Monads and Other Functional Paradigms in Practice](https://realm.io/news/slug-raheel-ahmad-using-monads-functional-paradigms-in-practice-functors-patterns-swift/)

[Swift Functors, Applicatives, and Monads in Pictures](http://www.mokacoding.com/blog/functor-applicative-monads-in-pictures/)

[Functor and Monad in Swift ](http://www.javiersoto.me/post/106875422394)

[What The Heck Is A Monad](http://khanlou.com/2015/09/what-the-heck-is-a-monad/)

# S
-------

### STACK

When a method (or function) is executed, a chunk of memory is allocated from a part of memory called the stack. This chunk of memory is called a frame, and the frame stores the values for variables declared inside the method. A variable declared inside a method is called a local variable.

* The stack is always reserved in a LIFO(Last in first out) order, the most recently reserved block is always the next block to be freed.

* Stack segment is used to store local variable.

* Variables created on the stack will go out of scope and automatically deallocate.

* Much faster to allocate in comparison to variables on the heap.

* Usually has a maximum size already determined when your program starts

![](https://vikashazrati.files.wordpress.com/2007/10/stacknheap.png?raw=true)

#### LINKS
[iOS Programming: The Big Nerd Ranch Guide 5th Edition](https://www.bignerdranch.com/we-write/ios-programming/)

[What is the difference between the stack and the heap?](https://www.quora.com/What-is-the-difference-between-the-stack-and-the-heap)

[What and where are the stack and heap?](http://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap)

[Stack and Heap](https://vikashazrati.wordpress.com/2007/10/01/quicktip-java-basics-stack-and-heap/)

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
