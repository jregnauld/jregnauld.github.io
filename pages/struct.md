layout: page
title: Because you need to know your stuffs
permalink: /struct/
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
# Binary Search

* Goal: Quickly find an element in an array.

* Binary search is recursive in nature because you apply the same logic over and over again to smaller and smaller subarrays

* To split the array in half, we need to know the index of the object in the middle.

```
[ 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67 ]
                                  *
```

```
[ x, x, x, x, x, x, x, x, x, x | 31, 37, 41, 43, 47, 53, 59, 61, 67 ]
```

```
[ x, x, x, x, x, x, x, x, x, x | 31, 37, 41, 43, 47, 53, 59, 61, 67 ]
                                                 *
```
etc

```
if a[midIndex] > key {
    // use left half
} else if a[midIndex] < key {
    // use right half
} else {
    return midIndex
}
```

# Binary Search Tree

* A binary search tree is a special kind of binary tree (a tree in which each node has at most two children) that performs insertions and deletions such that the tree is always sorted.

* If the value is less than the current node, then take the left branch.

* If the value is greater than the current node, take the right branch.

* And if the value is equal to the current node, we've found it!

# Breadth-First Search

* Breadth-first search (BFS) is an algorithm for traversing or searching tree or graph data structures. It starts at a source node and explores the immediate neighbor nodes first, before moving to the next level neighbors.

* Breadth-first search can be used to solve many problems. A small selection:
  * Computing the shortest path between a source node and each of the other nodes (only for unweighted graphs).
  * Calculating the minimum spanning tree on an unweighted graph.

# Depth-First Search

* Depth-first search (DFS) is an algorithm for traversing or searching tree or graph data structures. It starts at a source node and explores as far as possible along each branch before backtracking.

* Depth-first search can be used to solve many problems, for example:

  * Finding connected components of a sparse graph
  * Topological sorting of nodes in a graph
  * Finding bridges of a graph (see: Bridges)

# Graph

* a graph is a set of vertices paired with a set of edges. The vertices are the round things and the edges are the lines between them. Edges connect a vertex to other vertices.
* example: facebook, list of the tasks that needs to be finsh, aeroport links

# Hash Table

* At its most basic, a hash table is nothing more than an array. Initially, this array is empty. When you put a value into the hash table under a certain key, it uses that key to calculate an index in the array,

* the hash table takes the key "firstName" and asks it for its hashValue property. That's why keys must be Hashable.

* A common way to make these big numbers more suitable is to first make the hash positive and then take the modulo with the array size.
  * Our array has size 5, so the index for the "firstName" key becomes abs(-4799450059917011053) % 5 = 3. You can calculate for yourself that the array index for "hobbies" is 1.

# Heap

* A heap is a binary tree that lives inside an array, so it doesn't use parent/child pointers. The tree is partially sorted according to something called the "heap property" that determines the order of the nodes in the tree.

* There are two kinds of heaps: a max-heap and a min-heap. They are identical, except that the order in which they store the tree nodes is opposite.

* In a max-heap, parent nodes must always have a greater value than each of their children. For a min-heap it's the other way around: every parent node has a smaller value than its child nodes. This is called the "heap property" and it is true for every single node in the tree.

# Linked List

* A linked list is a sequence of data items, just like an array. But where an array allocates a big block of memory to store the objects, the elements in a linked list are totally separate objects in memory and are connected through links:

```
+--------+    +--------+    +--------+    +--------+
|        |    |        |    |        |    |        |
| node 0 |--->| node 1 |--->| node 2 |--->| node 3 |
|        |    |        |    |        |    |        |
+--------+    +--------+    +--------+    +--------+
```

The elements of a linked list are referred to as nodes. The above picture shows a singly linked list, where each node only has a reference -- or a "pointer" -- to the next node. In a doubly linked list, shown below, nodes also have pointers to the previous node:

```
+--------+    +--------+    +--------+    +--------+
|        |--->|        |--->|        |--->|        |
| node 0 |    | node 1 |    | node 2 |    | node 3 |
|        |<---|        |<---|        |<---|        |
+--------+    +--------+    +--------+    +--------+
```
You need to keep track of where the list begins. That's usually done with a pointer called the head

```
public class LinkedListNode<T> {
  var value: T
  var next: LinkedListNode?
  weak var previous: LinkedListNode?

  public init(value: T) {
    self.value = value
  }
}
```

```
public class LinkedList<T> {
  public typealias Node = LinkedListNode<T>

  private var head: Node?

  public var isEmpty: Bool {
    return head == nil
  }

  public var first: Node? {
    return head
  }
}
```



# Merge Sort

* Put the numbers in a pile. The pile is unsorted.

* Split the pile into 2. Now you have two unsorted piles of numbers.

* Keep splitting the resulting piles until you can't split anymore. In the end, you will have n piles with 1 number in each pile.

* Begin to merge the piles together by sequentially pairing a pile with another pile. During each merge, you put the contents in sorted order. This is fairly easy because each individual pile is already sorted.

```
func mergeSort(_ array: [Int]) -> [Int] {
  guard array.count > 1 else { return array }    // 1

  let middleIndex = array.count / 2              // 2

  let leftArray = mergeSort(Array(array[0..<middleIndex]))             // 3

  let rightArray = mergeSort(Array(array[middleIndex..<array.count]))  // 4

  return merge(leftPile: leftArray, rightPile: rightArray)             // 5
}
```

```
func merge(leftPile: [Int], rightPile: [Int]) -> [Int] {
  // 1
  var leftIndex = 0
  var rightIndex = 0

  // 2
  var orderedPile = [Int]()

  // 3
  while leftIndex < leftPile.count && rightIndex < rightPile.count {
    if leftPile[leftIndex] < rightPile[rightIndex] {
      orderedPile.append(leftPile[leftIndex])
      leftIndex += 1
    } else if leftPile[leftIndex] > rightPile[rightIndex] {
      orderedPile.append(rightPile[rightIndex])
      rightIndex += 1
    } else {
      orderedPile.append(leftPile[leftIndex])
      leftIndex += 1
      orderedPile.append(rightPile[rightIndex])
      rightIndex += 1
    }
  }

  // 4
  while leftIndex < leftPile.count {
    orderedPile.append(leftPile[leftIndex])
    leftIndex += 1
  }

  while rightIndex < rightPile.count {
    orderedPile.append(rightPile[rightIndex])
    rightIndex += 1
  }

  return orderedPile
}
```

# Queue

* A queue is a list where you can only insert new items at the back and remove items from the front. This ensures that the first item you enqueue is also the first item you dequeue. First come, first serve!

* A queue gives you a FIFO or first-in, first-out order. The element you inserted first is also the first one to come out again. It's only fair! (A very similar data structure, the stack, is LIFO or last-in first-out.)

# Quicksort

* Goal: Sort an array from low to high (or high to low).
```
[ 10, 0, 3, 9, 2, 14, 8, 27, 1, 5, 8, -1, 26 ]

```

```
less:    [ 0, 3, 2, 1, 5, -1 ]
equal:   [ 8, 8 ]
greater: [ 10, 9, 14, 27, 26 ]
```

```
func quicksort<T: Comparable>(_ a: [T]) -> [T] {
  guard a.count > 1 else { return a }

  let pivot = a[a.count/2]
  let less = a.filter { $0 < pivot }
  let equal = a.filter { $0 == pivot }
  let greater = a.filter { $0 > pivot }

  return quicksort(less) + equal + quicksort(greater)
}
```
# Stack

* A stack is like an array but with limited functionality. You can only push to add a new element to the top of the stack, pop to remove the element from the top, and peek at the top element without popping it off.

* A stack gives you a LIFO or last-in first-out order. The element you pushed last is the first one to come off with the next pop. (A very similar data structure, the queue, is FIFO or first-in first-out.)


# Tree

* A tree consists of nodes, and these nodes are linked to one another.

* Nodes have links to their children and usually to their parent as well. The children are the nodes below a given node; the parent is the node above. A node always has just one parent but can have multiple children.

* Such a structure is called a graph. A tree is really a very simple form of a graph. (In a similar vein, a linked list is a simple version of a tree. Think about it!)

```
public class TreeNode<T> {
  public var value: T

  public var parent: TreeNode?
  public var children = [TreeNode<T>]()

  public init(value: T) {
    self.value = value
  }

  public func addChild(_ node: TreeNode<T>) {
    children.append(node)
    node.parent = self
  }
}
```
