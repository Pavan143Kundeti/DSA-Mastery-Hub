# Rotate Array by K Positions

## Problem Statement
Given an array, rotate the array to the right by `k` steps, where `k` is non-negative.

## What is Array Rotation?
Array rotation means moving elements from one position to another in a circular manner.
- **Right rotation**: Elements move towards the end, last elements wrap to beginning
- **Left rotation**: Elements move towards the start, first elements wrap to end

## Example
```
Input: nums = [1, 2, 3, 4, 5], k = 2
Output: [4, 5, 1, 2, 3]

Input: nums = [1, 2, 3, 4, 5], k = 3  
Output: [3, 4, 5, 1, 2]
```

## Visual Representation
```
Original: [1, 2, 3, 4, 5]
k = 2 (rotate right by 2 positions)

Step 1: [5, 1, 2, 3, 4] (rotate by 1)
Step 2: [4, 5, 1, 2, 3] (rotate by 1 more)

Result: [4, 5, 1, 2, 3]
```

## Approach 1: Brute Force Method

### Logic
- For each rotation step, move last element to front
- Repeat this process k times
- Use pop() and insert() operations

### Code Implementation
```python
def rotate_array_brute_force(arr, k):
    # Handle edge cases
    if not arr or k == 0:
        return arr
    
    # Reduce unnecessary rotations
    k = k % len(arr)
    
    # Rotate k times
    for i in range(k):
        # Remove last element
        last_element = arr.pop()
        # Insert at beginning
        arr.insert(0, last_element)
    
    return arr

# Test the function
nums = [1, 2, 3, 4, 5]
k = 2
print("Before rotation:", nums)
result = rotate_array_brute_force(nums.copy(), k)
print("After rotation:", result)
```

### Code Explanation Line by Line

| Line | Code | Explanation |
|------|------|-------------|
| 1 | `k = k % len(arr)` | Reduce k to avoid unnecessary full rotations |
| 2 | `for i in range(k):` | Repeat rotation k times |
| 3 | `last_element = arr.pop()` | Remove and get last element (O(1) operation) |
| 4 | `arr.insert(0, last_element)` | Insert element at beginning (O(n) operation) |

### Why k % len(arr)?
```python
# Example: arr = [1, 2, 3, 4, 5], k = 7
# Array length = 5
# After 5 rotations, array returns to original state
# So k = 7 is same as k = 7 % 5 = 2
# This saves unnecessary rotations
```

### Time Complexity: O(n × k)
- **pop() operation**: O(1) - removes from end
- **insert(0, element)**: O(n) - shifts all elements right
- **Total**: O(n) × k times = O(n × k)

### Space Complexity: O(1)
- Modifies array in-place

## Approach 2: Optimal Method (Array Slicing)

### Logic
- Split array into two parts at rotation point
- Combine parts in rotated order
- Use Python's negative indexing and slicing

### Code Implementation
```python
def rotate_array_optimal(arr, k):
    # Handle edge cases
    if not arr or k == 0:
        return arr
    
    # Reduce unnecessary rotations
    k = k % len(arr)
    
    # Split and combine using slicing
    return arr[-k:] + arr[:-k]

# Test the function
nums = [1, 2, 3, 4, 5]
k = 2
print("Before rotation:", nums)
result = rotate_array_optimal(nums, k)
print("After rotation:", result)
```

### Understanding Array Slicing
```python
# For arr = [1, 2, 3, 4, 5], k = 2

# arr[-k:] means arr[-2:]
# This selects last 2 elements: [4, 5]

# arr[:-k] means arr[:-2]  
# This selects all except last 2: [1, 2, 3]

# Combine: [4, 5] + [1, 2, 3] = [4, 5, 1, 2, 3]
```

### Negative Indexing in Python
```python
# Array: [1, 2, 3, 4, 5]
# Index:  0  1  2  3  4  (positive)
# Index: -5 -4 -3 -2 -1  (negative)

# arr[-1] = 5 (last element)
# arr[-2] = 4 (second last element)
# arr[-k:] = last k elements
# arr[:-k] = all except last k elements
```

### Time Complexity: O(n)
- **Slicing operations**: O(n) - creates new arrays
- **Concatenation**: O(n) - combines arrays
- **Total**: O(n)

### Space Complexity: O(n)
- Creates new arrays for slicing

## Step-by-Step Trace Example

### For Array [1, 2, 3, 4, 5], k = 3:

**Brute Force Method:**
```python
Initial: [1, 2, 3, 4, 5], k = 3

# Rotation 1:
# pop() → last_element = 5
# insert(0, 5) → [5, 1, 2, 3, 4]

# Rotation 2:  
# pop() → last_element = 4
# insert(0, 4) → [4, 5, 1, 2, 3]

# Rotation 3:
# pop() → last_element = 3  
# insert(0, 3) → [3, 4, 5, 1, 2]

Final: [3, 4, 5, 1, 2]
```

**Optimal Method:**
```python
arr = [1, 2, 3, 4, 5], k = 3

# k % len(arr) = 3 % 5 = 3

# arr[-k:] = arr[-3:] = [3, 4, 5] (last 3 elements)
# arr[:-k] = arr[:-3] = [1, 2] (all except last 3)

# Result: [3, 4, 5] + [1, 2] = [3, 4, 5, 1, 2]
```

## Complete Working Example
```python
def demonstrate_array_rotation():
    test_cases = [
        ([1, 2, 3, 4, 5], 2),
        ([1, 2, 3, 4, 5], 3),
        ([1, 2, 3, 4, 5], 7),  # k > array length
        ([1, 2], 1),
        ([1], 1),              # Single element
        ([], 3)                # Empty array
    ]
    
    print("=== Array Rotation Demo ===")
    
    for i, (nums, k) in enumerate(test_cases, 1):
        if not nums:
            print(f"\nTest Case {i}: Empty array")
            continue
            
        print(f"\nTest Case {i}:")
        print(f"Original: {nums}, k = {k}")
        
        # Brute Force Method
        brute_result = rotate_array_brute_force(nums.copy(), k)
        print(f"Brute Force: {brute_result}")
        
        # Optimal Method
        optimal_result = rotate_array_optimal(nums, k)
        print(f"Optimal: {optimal_result}")

# Run the demonstration
demonstrate_array_rotation()
```

## Method Comparison

| Aspect | Brute Force | Optimal |
|--------|-------------|---------|
| **Time Complexity** | O(n × k) | O(n) |
| **Space Complexity** | O(1) | O(n) |
| **In-place Modification** | Yes | No (creates new array) |
| **Code Simplicity** | Multiple operations | Single line |
| **Best for** | Small k values | Large k values |

## Key Insights

### When to Use Each Method?
1. **Small Arrays + Small k**: Brute force is fine
2. **Large Arrays + Large k**: Optimal method is better
3. **Memory Constraints**: Brute force (in-place)
4. **Speed Priority**: Optimal method

### Important Edge Cases
```python
# k = 0: No rotation needed
# k = len(arr): Full rotation (same as original)
# k > len(arr): Use k % len(arr)
# Empty array: Return as is
# Single element: Always same result
```

## Interview Tips
1. **Ask About Constraints**: In-place modification required?
2. **Handle Edge Cases**: Empty array, k = 0, k > array length
3. **Explain k % len(arr)**: Why this optimization matters
4. **Discuss Trade-offs**: Time vs space complexity
5. **Show Both Methods**: Demonstrates problem-solving range

## Common Mistakes
- **Not handling k > array length**: Causes unnecessary operations
- **Wrong slicing syntax**: Confusing positive/negative indexing
- **Modifying original array**: When new array is expected
- **Off-by-one errors**: In rotation counting

## LeetCode Connection
This problem appears as **LeetCode 189: Rotate Array** (Medium difficulty). The optimal solution uses similar concepts but may require in-place modification using array reversal technique.

## Practice Variations
1. Rotate array to the left by k positions
2. Find minimum rotations to make array sorted
3. Check if one array is rotation of another
4. Rotate 2D matrix by 90 degrees

This problem teaches fundamental array manipulation and introduces important concepts like modular arithmetic and Python slicing techniques.