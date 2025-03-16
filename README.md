# Computer Olympiad Curriculum Book

## Table of Contents

1. [Introduction](#introduction)
2. [Sequential and Binary Search](#sequential-and-binary-search)
   - Sequential Search
   - Binary Search
   - Comparison
3. [Search by Elimination](#search-by-elimination)
   - Concept
   - Ternary Search Algorithm
   - Applications
4. [Binary Heap and Binary Search Tree](#binary-heap-and-binary-search-tree)
   - Binary Heap
   - Binary Search Tree (BST)
   - Comparison
5. [Exercises](#exercises)
   - Search Exercises
   - Elimination Exercises
   - Heap and BST Exercises
6. [Sample Exam](#sample-exam)

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

## Sample Exam

1. Explain sequential vs binary search with code and complexity analysis.
2. Implement ternary search for optimization problems.
3. Show heap operations and their complexity.
4. Solve a BST operation-based problem and analyze its complexity.

---

