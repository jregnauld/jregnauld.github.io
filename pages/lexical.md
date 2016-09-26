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
The page contains all of my research as a note and ordered by letters.


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

* no tracking involved: fast

* ARC just inserts the code to add a pointer to that every time the object is assigned to a new weak reference.

#### LINKS
[Zeroing Weak References](https://www.mikeash.com/pyblog/friday-qa-2010-07-16-zeroing-weak-references-in-objective-c.html)

[How does the ARC's zeroing weak pointer behavior implemented?](http://stackoverflow.com/questions/8859666/how-does-the-arcs-zeroing-weak-pointer-behavior-implemented)
