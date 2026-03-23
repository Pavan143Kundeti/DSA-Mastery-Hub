# Time Complexity Guide - DSA Fundamentals

## What is Time Complexity?

Time complexity tells us how our code will perform as the input size grows. It's a way to measure the efficiency of algorithms using **Big O Notation**.

**Big O Notation**: Written as O(something) - uses a capital letter "O" to represent how an algorithm's runtime grows with input size.

## Types of Time Complexity

| Type | Notation | Description | Example |
|------|----------|-------------|---------|
| Constant | O(1) | Same time regardless of input size | Accessing array element by index |
| Logarithmic | O(log n) | Time grows slowly with input | Binary search |
| Linear | O(n) | Time grows directly with input | Printing all array elements |
| Quadratic | O(n²) | Time grows with square of input | Nested loops |
| Exponential | O(2^n) | Time doubles with each addition | Recursive functions with multiple calls |

## 1. Constant Time - O(1)

**What it means**: No matter how big your array is, the operation takes the same time.

**Example**: Getting an element from array using index
```python
def constant_time_example(arr):
    return arr[0]  # Always takes same time
```

**Real-world analogy**: Like finding a book when you know the exact shelf number - doesn't matter if library has 100 or 10,000 books.

## 2. Linear Time - O(n)

**What it means**: If array has 10 elements, you do 10 operations. If it has 100 elements, you do 100 operations.

**Example**: Printing all elements in an array
```python
def linear_time_example(arr):
    for element in arr:
        print(element)  # Visits each element once
```

**Why O(n)**: We use a for loop that goes from first to last element. The time increases directly with array size.

## 3. Quadratic Time - O(n²)

**What it means**: Nested loops - a loop inside another loop.

**Example**: Printing all pairs from an array
```python
def quadratic_time_example(arr):
    for i in arr:
        for j in arr:
            print(i, j)  # For each element, check with every other element
```

**Output pattern**: If array = [1,2,3], output will be:
- 1,1  1,2  1,3
- 2,1  2,2  2,3  
- 3,1  3,2  3,3

## 4. Logarithmic Time - O(log n)

**What it means**: Between constant and linear time. We don't check every element, but more than just one.

**Key concept**: We eliminate half the possibilities in each step.

**Example**: Binary Search (finding element in sorted array)
```python
def binary_search(arr, target):
    left = 0
    right = len(arr) - 1
    
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1  # Search right half
        else:
            right = mid - 1  # Search left half
```

**How it works**:
1. Start with array of 30 elements
2. Check middle element (position 15)
3. If target is larger, ignore left half (now only 15 elements to check)
4. Check middle of remaining half
5. Keep halving until found

**Important**: Binary search only works on **sorted arrays**.

## 5. Exponential Time - O(2^n)

**What it means**: Time doubles with each additional input.

**Real-world analogy**: Folding paper
- 1 fold = 2 pieces
- 2 folds = 4 pieces  
- 3 folds = 8 pieces
- Each fold doubles the pieces

**Example**: Recursive functions that call themselves multiple times
```python
def exponential_example(n):
    if n <= 1:
        return 1
    return exponential_example(n-1) + exponential_example(n-1)
```

## Time Complexity Comparison

| Input Size | O(1) | O(log n) | O(n) | O(n²) | O(2^n) |
|------------|------|----------|------|-------|--------|
| 1 | 1 | 1 | 1 | 1 | 2 |
| 10 | 1 | 3 | 10 | 100 | 1,024 |
| 100 | 1 | 7 | 100 | 10,000 | 2^100 |
| 1000 | 1 | 10 | 1,000 | 1,000,000 | 2^1000 |

## Performance Ranking (Best to Worst)

1. **O(1)** - Constant (Best)
2. **O(log n)** - Logarithmic  
3. **O(n)** - Linear
4. **O(n²)** - Quadratic
5. **O(2^n)** - Exponential (Worst)

## Key Points to Remember

- **O(1)**: Direct access, no loops
- **O(n)**: Single loop through data
- **O(n²)**: Nested loops (loop inside loop)
- **O(log n)**: Divide and conquer (like binary search)
- **O(2^n)**: Recursive functions with multiple calls

## Why Time Complexity Matters

1. **Scalability**: Helps predict how code performs with large datasets
2. **Optimization**: Identify bottlenecks in your code
3. **Algorithm Selection**: Choose the best algorithm for your problem
4. **Interview Preparation**: Common topic in technical interviews

## Practical Tips

- Always analyze your loops: single loop = O(n), nested loops = O(n²)
- Direct array access is always O(1)
- Sorting algorithms are typically O(n log n)
- Avoid exponential time algorithms for large inputs
- When in doubt, trace through your code step by step

## Visualization Tool

For better understanding, use **Python Tutor** online:
1. Search "Python Tutor" in Google
2. Click "Edit and get help"
3. Paste your code and click "Visualize Execution"
4. Step through each operation to see how time complexity works

Remember: Understanding time complexity takes practice. Don't worry if it seems confusing at first - it becomes clearer as you solve more problems!