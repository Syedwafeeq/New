# Trees - Data Structures and Algorithms

A comprehensive collection of Tree Data Structure implementations, algorithms, and interview-focused problems. This repository serves as a structured resource for learning, practicing, and mastering tree-related concepts commonly encountered in software engineering interviews, competitive programming, and real-world applications.

---

## Overview

Trees are hierarchical, non-linear data structures consisting of nodes connected by edges. They are fundamental to computer science and form the backbone of numerous systems, including databases, operating systems, compilers, file systems, and search engines.

This repository contains implementations, explanations, and problem solutions covering basic to advanced tree concepts.

---

## Topics Covered

### Tree Fundamentals

* Tree Terminology
* Node and Edge Concepts
* Height and Depth
* Levels in a Tree
* Degree of a Node
* Leaf Nodes
* Internal Nodes
* Ancestors and Descendants

### Binary Trees

* Binary Tree Representation
* Recursive Traversals
* Iterative Traversals
* Height of Binary Tree
* Diameter of Binary Tree
* Maximum Depth
* Balanced Binary Tree
* Symmetric Tree
* Boundary Traversal
* Vertical Traversal
* Zigzag Traversal
* Level Order Traversal
* Top View
* Bottom View
* Left View
* Right View

### Binary Search Trees (BST)

* Search in BST
* Insertion
* Deletion
* Validation of BST
* Lowest Common Ancestor
* Kth Smallest Element
* Kth Largest Element
* BST Iterator
* Recover Binary Search Tree

---

```text
Trees/
│
├── Basics/
│   ├── Introduction
│   ├── Height of Tree
│   ├── Count Nodes
│   └── Leaf Nodes
│
├── Traversals/
│   ├── Inorder Traversal
│   ├── Preorder Traversal
│   ├── Postorder Traversal
│   ├── Level Order Traversal
│   └── Iterative Traversals
│
├── BinaryTree/
│   ├── Diameter
│   ├── Balanced Tree
│   ├── Maximum Path Sum
│   ├── Boundary Traversal
│   ├── Vertical Traversal
│   └── Tree Views
│
├── BST/
    ├── Search
    ├── Insert
    ├── Delete
    ├── Validate BST
    └── Kth Smallest
```

---

## Tree Traversals

### Inorder Traversal

```text
Left → Root → Right
```

### Preorder Traversal

```text
Root → Left → Right
```

### Postorder Traversal

```text
Left → Right → Root
```

### Level Order Traversal

```text
Breadth First Search (BFS)
```

---

## Binary Search Tree Property

For every node:

```text
All values in Left Subtree  <  Root Value
All values in Right Subtree >  Root Value
```

This property enables efficient searching, insertion, and deletion operations.

---

## Time Complexity Reference

| Operation | Binary Tree | BST Average | BST Worst |
| --------- | ----------- | ----------- | --------- |
| Search    | O(n)        | O(log n)    | O(n)      |
| Insert    | O(n)        | O(log n)    | O(n)      |
| Delete    | O(n)        | O(log n)    | O(n)      |
| Traversal | O(n)        | O(n)        | O(n)      |

---

### Easy

* Tree Traversals
* Height of Tree
* Count Nodes
* Leaf Node Count
* Maximum Depth

### Medium

* Diameter of Tree
* Balanced Binary Tree
* Lowest Common Ancestor
* Path Sum Problems
* Level Order Traversal
* Zigzag Traversal
* Tree Views

### Hard

* Maximum Path Sum
* Vertical Order Traversal
* Boundary Traversal
* BST Validation
* Serialize and Deserialize Tree
* Binary Lifting
* Segment Trees
* Trie Problems

---

## Learning Roadmap

### Phase 1: Fundamentals

* Tree Terminology
* Binary Trees
* Recursive Traversals
* Iterative Traversals

### Phase 2: Core Binary Tree Problems

* Height
* Diameter
* Balanced Trees
* Path Problems
* Level Order Traversal

### Phase 3: Binary Search Trees

* Search
* Insert
* Delete
* Validation
* Kth Smallest Element
---

## Applications of Trees

Trees are widely used in:

* Database Indexing
* File Systems
* Search Engines
* Network Routing
* Compilers
* Artificial Intelligence
* Decision Trees
* Autocomplete Systems
* Operating Systems

---

## Contribution Guidelines

Contributions are welcome.

If you would like to contribute:

1. Fork the repository.
2. Create a feature branch.
3. Add your implementation or improvements.
4. Commit your changes.
5. Open a Pull Request.
---
