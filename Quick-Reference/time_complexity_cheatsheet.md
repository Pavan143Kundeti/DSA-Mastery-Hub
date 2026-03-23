# ⚡ Time Complexity Quick Reference

## Big O Notation Cheat Sheet

| Notation | Name | Example | Performance |
|----------|------|---------|-------------|
| O(1) | Constant | Array access | ⭐⭐⭐⭐⭐ Excellent |
| O(log n) | Logarithmic | Binary search | ⭐⭐⭐⭐ Very Good |
| O(n) | Linear | Simple loop | ⭐⭐⭐ Good |
| O(n log n) | Linearithmic | Merge sort | ⭐⭐ Fair |
| O(n²) | Quadratic | Nested loops | ⭐ Poor |
| O(2^n) | Exponential | Recursive fibonacci | ❌ Very Poor |

## Quick Identification

```python
# O(1) - Constant
arr[0]

# O(n) - Linear  
for i in arr:
    print(i)

# O(n²) - Quadratic
for i in arr:
    for j in arr:
        print(i, j)

# O(log n) - Logarithmic
# Binary search, divide and conquer

# O(2^n) - Exponential
# Recursive calls with multiple branches
```

## Common Data Structure Operations

| Data Structure | Access | Search | Insertion | Deletion |
|----------------|--------|--------|-----------|----------|
| Array | O(1) | O(n) | O(n) | O(n) |
| Linked List | O(n) | O(n) | O(1) | O(1) |
| Stack | O(n) | O(n) | O(1) | O(1) |
| Queue | O(n) | O(n) | O(1) | O(1) |
| Hash Table | O(1) | O(1) | O(1) | O(1) |
| Binary Tree | O(n) | O(n) | O(n) | O(n) |
| BST | O(log n) | O(log n) | O(log n) | O(log n) |

## Sorting Algorithms

| Algorithm | Best | Average | Worst | Space |
|-----------|------|---------|-------|-------|
| Bubble Sort | O(n) | O(n²) | O(n²) | O(1) |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | O(n) |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | O(log n) |
| Heap Sort | O(n log n) | O(n log n) | O(n log n) | O(1) |