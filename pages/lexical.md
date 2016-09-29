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
  - "iOS"
  - "iOS Programming"
  - "iOS Knowledge"
  - "iOS Interview"
  - "iOS Questions"

---

* The idea is to keep every note on something useful as short as possible.
* Because sometimes you want to have a quick reminder.
* One list to rule them all.

![](https://media.giphy.com/media/YLHwkqayc1j7a/giphy.gif)

# A
-------
### ADAPTER


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


##### LINKS
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

##### LINKS
[Clang wikipedia](https://en.wikipedia.org/wiki/Clang)

[Clang introduction](https://kevinaboos.wordpress.com/2013/07/23/clang-tutorial-part-i-introduction/)

[LLVM vs. GCC for iOS development](http://stackoverflow.com/questions/4589335/llvm-vs-gcc-for-ios-development)

### CONTRAVARIANCE

Contravariance is when supertypes are accepted. The parameters of overridden methods are contravariant.

Contravariant: an Animal[] is a Cat[]

##### LINKS
[Covariance and Contravariance](https://www.mikeash.com/pyblog/friday-qa-2015-11-20-covariance-and-contravariance.html)

[Covariance and contravariance](https://en.wikipedia.org/wiki/Covariance_and_contravariance_(computer_science))

### COVARIANCE

Covariance is when subtypes are accepted. Overridden read-only properties are covariant.

Covariant: a Cat[] is an Animal[]

##### LINKS
[Covariance and Contravariance](https://www.mikeash.com/pyblog/friday-qa-2015-11-20-covariance-and-contravariance.html)

[Covariance and contravariance](https://en.wikipedia.org/wiki/Covariance_and_contravariance_(computer_science))

### CURRYING
 Translating the evaluation of a function that takes multiple arguments into evaluating a sequence of functions, each with a single argument.

```
 function add (a, b) {
  return a + b;
}

add(3, 4); returns 7
```

```
 function add (a) {
  return function (b) {
    return a + b;
  }
}
```

```
 add(3)(4);

var add3 = add(3);

add3(4);
```

##### LINKS
[Introduction to Function Currying in Swift](https://robots.thoughtbot.com/introduction-to-function-currying-in-swift)

[What is 'Currying'?](http://stackoverflow.com/questions/36314/what-is-currying)

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

##### LINKS
[Using Monads and Other Functional Paradigms in Practice](https://realm.io/news/slug-raheel-ahmad-using-monads-functional-paradigms-in-practice-functors-patterns-swift/)

[Swift Functors, Applicatives, and Monads in Pictures](http://www.mokacoding.com/blog/functor-applicative-monads-in-pictures/)

[Functor and Monad in Swift ](http://www.javiersoto.me/post/106875422394)

[What The Heck Is A Monad](http://khanlou.com/2015/09/what-the-heck-is-a-monad/)

### FUTURE

Futures provide a way to reason about performing many operations in parallel– in an efficient and non-blocking way. A Future is a placeholder object for a value that may not yet exist. Generally, the value of the Future is supplied concurrently and can subsequently be used. Composing concurrent tasks in this way tends to result in faster, asynchronous, non-blocking parallel code.

##### LINKS
[Futures and Promises](http://docs.scala-lang.org/overviews/core/futures.html)

# G
-------

### GCC

The GNU Compiler Collection (GCC) is a compiler system produced by the GNU Project supporting various programming languages. It's not use anymore for iOS Project.

### GCD: GRAND CENTRAL DISPATCH
Technology to optimize application support for systems with multi-core processors and other symmetric multiprocessing systems.

* Implementation of task parallelism based on the thread pool pattern
* Move the management of the thread pool out of the hands of the developer and closer to the operating system.

##### Advantages

* Eliminate work on your part.

* Reduces the memory penalty your application pays for storing thread stacks in the application's memory space.

* Eliminates the code needed to create and configure your threads

* Eliminates the code needed to manage and schedule work on threads.

* Simplifies the code you have to write

##### LINKS
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

##### LINKS
[iOS Programming: The Big Nerd Ranch Guide 5th Edition](https://www.bignerdranch.com/we-write/ios-programming/)

[What is the difference between the stack and the heap?](https://www.quora.com/What-is-the-difference-between-the-stack-and-the-heap)

[What and where are the stack and heap?](http://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap)

[Stack and Heap](https://vikashazrati.wordpress.com/2007/10/01/quicktip-java-basics-stack-and-heap/)

#L
-------

### LLDB
LLDB is a high-performance debugger.
LLDB is the default debugger in Xcode on Mac OS X and supports debugging C, Objective-C and C++ on the desktop and iOS devices and simulator.

##### LINKS
[The LLDB Debugger](http://lldb.llvm.org/)

### LLVM
The LLVM(Low Level Virtual Machine) compiler infrastructure project  is a "collection of modular and reusable compiler and toolchain technologies" used to develop compiler front ends and back ends.
In Xcode, the LLVM compiler uses the Clang front end to parse source code and turn it into an interim format. Then the LLVM code generation layer (back end) turns that interim format into final machine code

##### LINKS
[LLVM Wikipedia](https://en.wikipedia.org/wiki/LLVM)

[Apple doc](https://developer.apple.com/library/content/documentation/CompilerTools/Conceptual/LLVMCompilerOverview/index.html)


# M
-------

### MANAGER

### MONADS

* A monad is a type of Functor

* A monad is a type that implements flatMap.

* A monad is a special kind of a functor. A functor F takes each type T and maps it to a new type FT. A burrito is like a functor: it takes a type, like meat or beans, and turns it into a new type, like beef burrito or bean burrito.

* Chain operations on contained value

![](http://adit.io/imgs/functors/recap.png?raw=true)

* functors: you apply a function to a wrapped value using map.

* applicatives: you apply a wrapped function to a wrapped value using apply, if defined.

* monads: you apply a function that returns a wrapped value, to a wrapped value using flatMap.

##### LINKS
[Using Monads and Other Functional Paradigms in Practice](https://realm.io/news/slug-raheel-ahmad-using-monads-functional-paradigms-in-practice-functors-patterns-swift/)

[Swift Functors, Applicatives, and Monads in Pictures](http://www.mokacoding.com/blog/functor-applicative-monads-in-pictures/)

[Functor and Monad in Swift ](http://www.javiersoto.me/post/106875422394)

[What The Heck Is A Monad](http://khanlou.com/2015/09/what-the-heck-is-a-monad/)

### MVC

### MVVM

### MVP


#R
-------

### REPOSITORY


### RETAIN CYCLE

A retain cycle is what happens when two objects both have strong references to each other. If 2 objects have strong references to each other, ARC will not generate the appropriate release message code on each instance since they are keeping each other alive.

![](https://static1.squarespace.com/static/5592eb03e4b051859f0b377f/5594defde4b0ad11495b5c4e/5594defde4b0ad11495b5c80/1435819784267/retain-cycle-copy.png?format=1000w&raw=true)

# S
-------

### SERVICE

### SOLID

* Single responsibility principle
  * a class should have only a single responsibility


* Open/closed principle
  * software entities … should be open for extension, but closed for modification


* Liskov substitution principle
  * objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program. ( you can use a cat instead of an animal, without issue.)


* Interface segregation principle
    * many client-specific interfaces are better than one general-purpose interface.


* Dependency inversion principle
  * one should “Depend upon Abstractions. Do not depend upon concretions.”

##### LINKS
[SOLID Wikipedia](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design))

[From STUPID to SOLID Code](http://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/)

### STACK

When a method (or function) is executed, a chunk of memory is allocated from a part of memory called the stack. This chunk of memory is called a frame, and the frame stores the values for variables declared inside the method. A variable declared inside a method is called a local variable.

* The stack is always reserved in a LIFO(Last in first out) order, the most recently reserved block is always the next block to be freed.

* Stack segment is used to store local variable.

* Variables created on the stack will go out of scope and automatically deallocate.

* Much faster to allocate in comparison to variables on the heap.

* Usually has a maximum size already determined when your program starts

![](https://vikashazrati.files.wordpress.com/2007/10/stacknheap.png?raw=true)

##### LINKS
[iOS Programming: The Big Nerd Ranch Guide 5th Edition](https://www.bignerdranch.com/we-write/ios-programming/)

[What is the difference between the stack and the heap?](https://www.quora.com/What-is-the-difference-between-the-stack-and-the-heap)

[What and where are the stack and heap?](http://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap)

[Stack and Heap](https://vikashazrati.wordpress.com/2007/10/01/quicktip-java-basics-stack-and-heap/)

# U

### UNOWNED
When two instances are related in such a way that one of the instances can’t exist without the other, the instance with the mandatory dependency needs to hold an unowned reference to the other instance.

* Use a weak reference whenever it is valid for that reference to become nil at some point during its lifetime. Conversely, use an unowned reference when you know that the reference will never be nil once it has been set during initialization.

##### LINKS
[Strong, Weak, and Unowned – Sorting out ARC and Swift](http://www.andrewcbancroft.com/2015/05/08/strong-weak-and-unowned-sorting-out-arc-and-swift/)

["WEAK, STRONG, UNOWNED, OH MY!" - A GUIDE TO REFERENCES IN SWIFT](http://krakendev.io/blog/weak-and-unowned-references-in-swift)

# V
-------

### VIPER

# W
-------

### WEAK
Weak is used to create a weak reference (pointer) to an object which does not participate in keeping that object alive.

##### WHEN
Where you want to keep a reference to an object, but don't want to keep that object in memory beyond its normal lifetime.

* Example: weak reference to self used in block can prevent retain cycle while ensuring that your program doesn't crash if the block is called after self is deallocated.

##### HOW
On dealloc, on object containing weak points will remove them from the internal mapping table that their target back to them.

Every class maintains a set of addresses of weak points that are pointing on it and when its dealloc is called its sets them all to zero.

* No tracking involved: fast

* ARC just inserts the code to add a pointer to that every time the object is assigned to a new weak reference.

* In Swift:
  * Weak pointers look like regular pointers in memory.
  * When a weak target's deinit runs, the target is not deallocated, and the weak pointer is not zeroed.
  * When the weak pointer is accessed after the target's deinit runs, it is zeroed on access and the weak target is deallocated.
  * The weak target contains a reference count for weak references, separate from the count of strong references.

##### LINKS
[Zeroing Weak References](https://www.mikeash.com/pyblog/friday-qa-2010-07-16-zeroing-weak-references-in-objective-c.html)

[How does the ARC's zeroing weak pointer behavior implemented?](http://stackoverflow.com/questions/8859666/how-does-the-arcs-zeroing-weak-pointer-behavior-implemented)

# Z
-------

### NSZOMBIE
