# Reverse an Array

## Problem Statement
Reverse the elements of a given array.

## What is Array Reversal?
Array reversal means changing the order of elements from first-to-last to last-to-first.

## Example
```
Input:  [1, 2, 3, 4, 5]
Output: [5, 4, 3, 2, 1]

Input:  [10, 20, 30]
Output: [30, 20, 10]
```

## Approach 1: Brute Force Method (Swapping)

### Logic
- Swap first element with last element
- Swap second element with second-last element
- Continue until we reach the middle
- Only need to loop till half of the array

### Why Only Half Loop?
```
Array: [1, 2, 3, 4, 5]
Index:  0  1  2  3  4

Step 1: Swap index 0 with index 4 → [5, 2, 3, 4, 1]
Step 2: Swap index 1 with index 3 → [5, 4, 3, 2, 1]
Step 3: Index 2 stays in middle (no swap needed)

We only need 2 swaps for 5 elements = n//2 iterations
```

### Code Implementation
```python
def reverse_array_brute_force(arr):
    # Get the length of array
    n = len(arr)
    
    # Loop only till half of the array
    for i in range(n // 2):
        # Swap first element with corresponding last element
        arr[i], arr[n - 1 - i] = arr[n - 1 - i], arr[i]
    
    return arr

# Test the function
array = [1, 2, 3, 4, 5]
print("Before:", array)
result = reverse_array_brute_force(array.copy())
print("After:", result)
```

### Code Explanation Line by Line

| Line | Code | Explanation |
|------|------|-------------|
| 1 | `n = len(arr)` | Store array length (5 for our example) |
| 2 | `for i in range(n // 2):` | Loop from 0 to 2 (half of 5 = 2) |
| 3 | `arr[i], arr[n - 1 - i] = ...` | Swap elements using Python tuple unpacking |

### Understanding the Swap Logic
```python
# When i = 0:
# arr[0] swaps with arr[5-1-0] = arr[4]
# Element at index 0 swaps with element at index 4

# When i = 1:
# arr[1] swaps with arr[5-1-1] = arr[3]  
# Element at index 1 swaps with element at index 3

# When i = 2: Loop stops (we've reached middle)
```

### Why `n // 2`?
- `//` is floor division (removes decimal part)
- For 5 elements: 5 // 2 = 2 (not 2.5)
- We need exactly 2 swaps to reverse 5 elements
- Middle element (index 2) stays in place

### Time Complexity: O(n/2) = O(n)
### Space Complexity: O(1)

## Approach 2: Optimal Method (Python Slicing)

### Using Negative Indexing
Python allows negative indexing where -1 refers to last element.

### Code Implementation
```python
def reverse_array_optimal(arr):
    # Use Python slicing with step -1
    return arr[::-1]

# Test the function
array = [1, 2, 3, 4, 5]
print("Before:", array)
result = reverse_array_optimal(array)
print("After:", result)
```

### Understanding Python Slicing
```python
# arr[start:end:step]
# arr[::-1] means:
# start: beginning (default)
# end: end (default) 
# step: -1 (reverse direction)

# This creates a new reversed array
```

### Time Complexity: O(n)
### Space Complexity: O(n) - creates new array

## Complete Working Example
```python
def demonstrate_array_reversal():
    # Test array
    original_array = [1, 2, 3, 4, 5]
    
    print("=== Array Reversal Demo ===")
    print(f"Original Array: {original_array}")
    
    # Method 1: Brute Force (modifies original)
    brute_force_array = original_array.copy()
    reverse_array_brute_force(brute_force_array)
    print(f"Brute Force Result: {brute_force_array}")
    
    # Method 2: Optimal (creates new array)
    optimal_result = reverse_array_optimal(original_array)
    print(f"Optimal Result: {optimal_result}")
    
    # Original array remains unchanged in optimal method
    print(f"Original Array: {original_array}")

# Run the demonstration
demonstrate_array_reversal()
```

## Key Differences Between Methods

| Aspect | Brute Force | Optimal |
|--------|-------------|---------|
| **Space Usage** | O(1) - modifies original | O(n) - creates new array |
| **Original Array** | Gets modified | Remains unchanged |
| **Code Length** | Multiple lines | Single line |
| **Understanding** | Shows swapping logic | Uses Python feature |

## Step-by-Step Trace Example

### For Array [1, 2, 3, 4, 5]:

```python
# Initial: [1, 2, 3, 4, 5]
# n = 5, so loop runs for i = 0, 1 (n//2 = 2 times)

# Iteration 1 (i = 0):
# Swap arr[0] with arr[5-1-0] = arr[4]
# Swap arr[0] with arr[4]
# [1, 2, 3, 4, 5] → [5, 2, 3, 4, 1]

# Iteration 2 (i = 1):  
# Swap arr[1] with arr[5-1-1] = arr[3]
# Swap arr[1] with arr[3]
# [5, 2, 3, 4, 1] → [5, 4, 3, 2, 1]

# Loop ends. Final result: [5, 4, 3, 2, 1]
```

## Important Notes

### Using `.copy()` Method
```python
# Wrong way - modifies original
result = reverse_array_brute_force(array)

# Right way - keeps original safe  
result = reverse_array_brute_force(array.copy())
```

### Why We Need `.copy()`?
- Arrays are passed by reference in Python
- Without `.copy()`, original array gets modified
- `.copy()` creates a separate copy to work with

## Interview Tips
1. **Explain the Logic**: Mention why we only loop till n//2
2. **Discuss Trade-offs**: Space vs readability
3. **Handle Edge Cases**: Empty arrays, single elements
4. **Show Both Methods**: Demonstrates problem-solving skills
5. **Trace Through Example**: Walk through step-by-step

## Common Mistakes
- **Full Loop**: Looping through entire array (reverses twice)
- **Index Errors**: Using wrong formula for last element
- **Modifying Original**: Not using `.copy()` when needed
- **Wrong Division**: Using `/` instead of `//` for integer division

## Practice Problems
1. Reverse only first half of array
2. Reverse array in groups of k elements
3. Check if array is same after reversing
4. Reverse array without using extra space

This problem teaches fundamental array manipulation and introduces Python's powerful slicing feature.