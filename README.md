# Computer Olympiad Curriculum Book

## Table of Contents

- [Computer Olympiad Curriculum Book](#computer-olympiad-curriculum-book)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Sequential and Binary Search](#sequential-and-binary-search)
    - [Sequential Search](#sequential-search)
      - [Implementation:](#implementation)
    - [Binary Search](#binary-search)
      - [Implementation:](#implementation-1)
    - [Comparison](#comparison)
  - [Search by Elimination](#search-by-elimination)
    - [Concept](#concept)
    - [Ternary Search Algorithm](#ternary-search-algorithm)
      - [Implementation:](#implementation-2)
    - [Applications](#applications)
  - [Binary Heap and Binary Search Tree](#binary-heap-and-binary-search-tree)
    - [Binary Heap](#binary-heap)
      - [Min-Heap Example:](#min-heap-example)
    - [Binary Search Tree (BST)](#binary-search-tree-bst)
      - [Basic Operations:](#basic-operations)
    - [Comparison](#comparison-1)
  - [Exercises](#exercises)
    - [Search Exercises](#search-exercises)
    - [Elimination Exercises](#elimination-exercises)
    - [Heap and BST Exercises](#heap-and-bst-exercises)
  - [Practical problems](#practical-problems)
  - [Sequential and Binary Search Problems](#sequential-and-binary-search-problems)
  - [Search by Elimination Problems](#search-by-elimination-problems)

---

## Introduction
Welcome to the Computer Olympiad Curriculum. This book-style curriculum aims to provide comprehensive knowledge, practical exercises, and evaluation methods for mastering core concepts in search algorithms and data structures using C++.

---

## Sequential and Binary Search

### Sequential Search
Sequential search is the simplest search method that examines each element sequentially until the desired element is found.

#### Implementation:
```cpp
int sequentialSearch(int arr[], int size, int target) {
    for (int i = 0; i < size; ++i) {
        if (arr[i] == target) return i;
    }
    return -1;
}
```

### Binary Search
Binary search works efficiently on sorted arrays by repeatedly dividing the search interval in half.

#### Implementation:
```cpp
int binarySearch(int arr[], int left, int right, int target) {
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target) return mid;
        if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
```

### Comparison
| Algorithm | Best Case | Average Case | Worst Case |
|-----------|-----------|--------------|------------|
| Sequential Search | O(1) | O(n) | O(n) |
| Binary Search | O(1) | O(log n) | O(log n) |

---

## Search by Elimination

### Concept
Search by elimination reduces the search space efficiently by removing irrelevant data sections.

### Ternary Search Algorithm
An efficient search method for unimodal functions by dividing search space into three parts.

#### Implementation:
```cpp
int ternarySearch(int arr[], int left, int right, int target) {
    while (left <= right) {
        int mid1 = left + (right - left) / 3;
        int mid2 = right - (right - left) / 3;
        if (arr[mid1] == target) return mid1;
        if (arr[mid2] == target) return mid2;
        if (target < arr[mid1]) right = mid1 - 1;
        else if (target > arr[mid2]) left = mid2 + 1;
        else {
            left = mid1 + 1;
            right = mid2 - 1;
        }
    }
    return -1;
}
```

### Applications
- Finding the minimum or maximum in unimodal functions.
- Optimization problems in programming contests.

---

## Binary Heap and Binary Search Tree

### Binary Heap
A binary heap is a complete binary tree with specific heap properties, useful for priority queues.

#### Min-Heap Example:
```cpp
priority_queue<int, vector<int>, greater<int>> minHeap;
```

### Binary Search Tree (BST)
A BST efficiently supports dynamic set operations.

#### Basic Operations:
```cpp
struct Node {
    int data;
    Node *left, *right;
    Node(int val) : data(val), left(nullptr), right(nullptr) {}
};

Node* insert(Node* root, int key) {
    if (!root) return new Node(key);
    if (key < root->data) root->left = insert(root->left, key);
    else root->right = insert(root->right, key);
    return root;
}
```

### Comparison
- **Heap**: Fastest for priority access, suitable for priority queues.
- **BST**: Efficient for dynamic operations like insertion, deletion, and search.

---

## Exercises

### Search Exercises
1. Implement both sequential and binary search.
2. Compare their runtime performance with different data sizes.

### Elimination Exercises
1. Implement and test ternary search.
2. Solve practical problems using elimination strategies.

### Heap and BST Exercises
1. Implement heap operations (insert, delete).
2. Demonstrate various BST operations (insert, delete, search).

---

## Practical problems

## Sequential and Binary Search Problems

1. [A. Vika and the Bridge](https://codeforces.com/problemset/problem/1848/B)
2. [B. Dolce Vita](https://codeforces.com/problemset/problem/1671/C)
3. [C. Fibonaccharsis](https://codeforces.com/problemset/problem/1853/B)
4. [D. Chloe and the Sequence](https://codeforces.com/problemset/problem/743/B)
5. [E. Two Cakes](https://codeforces.com/problemset/problem/911/B)
6. [F. Planning The Expedition](https://codeforces.com/problemset/problem/1011/B)
7. [G. NN and the Optical Illusion](https://codeforces.com/problemset/problem/1100/C)
8. [H. Sanatorium](https://codeforces.com/problemset/problem/732/C)
9. [I. Eugeny and Play List](https://codeforces.com/problemset/problem/302/B)
10. [J. Megacity](https://codeforces.com/problemset/problem/424/B)

## Search by Elimination Problems

1. [A. Balanced Stone Heaps](https://codeforces.com/problemset/problem/1623/C)
2. [B. Kuro and GCD and XOR and SUM](https://codeforces.com/problemset/problem/979/D)
3. [C. NN country](https://codeforces.com/problemset/problem/983/E)
4. [D. Sonya and Ice Cream](https://codeforces.com/problemset/problem/1004/E)
5. [E. Split the Tree](https://codeforces.com/problemset/problem/1059/E)
6. [F. Company](https://codeforces.com/problemset/problem/1062/E)
7. [G. Construct a tree](https://codeforces.com/problemset/problem/1098/C)
8. [H. Cookies](https://codeforces.com/problemset/problem/1099/F)
9. [I. Legendary Tree](https://codeforces.com/problemset/problem/1101/D)
10. [J. Tree Painting](https://codeforces.com/problemset/problem/1187/E)


---

