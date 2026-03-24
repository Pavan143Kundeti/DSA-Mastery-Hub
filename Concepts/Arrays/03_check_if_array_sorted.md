# Check if Array is Sorted

## Problem Statement
Check if a given array is sorted in ascending order or not.

## What is a Sorted Array?
A sorted array is an array where elements are arranged in a specific order:
- **Ascending Order**: Elements from smallest to largest (1, 2, 3, 4, 5)
- **Descending Order**: Elements from largest to smallest (5, 4, 3, 2, 1)

For this problem, we check if array is sorted in **ascending order**.

## Example
```
Input: [1, 2, 3, 4, 5]
Output: True (Sorted)

Input: [1, 3, 2, 4, 5]
Output: False (Not Sorted)
```

## Approach 1: Brute Force Method

### Logic
- Compare each element with the next element
- If any element is greater than the next element, return False
- If all comparisons pass, return True

### Algorithm Steps
1. Loop through array from index 0 to n-2 (second last element)
2. Compare arr[i] with arr[i+1]
3. If arr[i] > arr[i+1], return False
4. If loop completes, return True

### Code Implementation
```python
def is_sorted_brute_force(arr):
    # Loop through array except last element
    for i in range(len(arr) - 1):
        # If current element is greater than next element
        if arr[i] > arr[i + 1]:
            return False
    
    # If all comparisons pass, array is sorted
    return True

# Test the function
array = [1, 2, 3, 4, 5]
print("Sorted:", is_sorted_brute_force(array))  # Output: True

array = [1, 3, 2, 4, 5]
print("Sorted:", is_sorted_brute_force(array))  # Output: False
```

### Why len(arr) - 1?
- We compare each element with the next element
- Last element has no next element to compare
- So we loop till second last element (len(arr) - 1)
- This prevents "Index out of range" error

### Time Complexity: O(n)
### Space Complexity: O(1)

## Approach 2: Optimal Method (One Line)

### Using all() Function
Python provides `all()` function that returns True if all elements in an iterable are True.

### Code Implementation
```python
def is_sorted_optimal(arr):
    # Check if all adjacent pairs are in ascending order
    return all(arr[i] <= arr[i + 1] for i in range(len(arr) - 1))

# Test the function
array = [1, 2, 3, 4, 5]
print("Sorted:", is_sorted_optimal(array))  # Output: True

array = [1, 3, 2, 4, 5]
print("Sorted:", is_sorted_optimal(array))  # Output: False
```

### How all() Works
- `all()` returns True only if ALL conditions are True
- If any single condition is False, it returns False
- More concise than writing loops and if conditions

### Time Complexity: O(n)
### Space Complexity: O(1)

## Complete Example
```python
def check_array_sorted():
    # Test arrays
    test_arrays = [
        [1, 2, 3, 4, 5],      # Sorted
        [1, 3, 2, 4, 5],      # Not sorted
        [5, 4, 3, 2, 1],      # Descending (not sorted for our case)
        [1, 1, 2, 2, 3],      # Sorted with duplicates
        [1]                   # Single element (sorted)
    ]
    
    print("Brute Force Method:")
    for arr in test_arrays:
        result = is_sorted_brute_force(arr)
        print(f"Array {arr}: {'Sorted' if result else 'Not Sorted'}")
    
    print("\nOptimal Method:")
    for arr in test_arrays:
        result = is_sorted_optimal(arr)
        print(f"Array {arr}: {'Sorted' if result else 'Not Sorted'}")

# Run the test
check_array_sorted()
```

## Key Points to Remember

| Aspect | Details |
|--------|---------|
| **Problem Type** | Array Traversal |
| **Comparison** | Adjacent elements |
| **Loop Range** | 0 to n-2 (to avoid index error) |
| **Return Logic** | False if any pair is wrong, True if all pass |
| **Edge Cases** | Single element, empty array, duplicates |

## Interview Tips
1. **Clarify Requirements**: Ask if duplicates are allowed
2. **Handle Edge Cases**: Single element arrays are considered sorted
3. **Explain Approach**: Mention why we use len(arr) - 1
4. **Time Complexity**: Both approaches are O(n)
5. **Space Optimization**: Both use O(1) extra space

## Common Mistakes
- **Index Error**: Forgetting to use len(arr) - 1 in loop
- **Wrong Comparison**: Using >= instead of > or vice versa
- **Edge Cases**: Not handling single element or empty arrays
- **Return Logic**: Forgetting to return True after loop completes

## Practice Problems
1. Check if array is sorted in descending order
2. Check if array is sorted (ascending or descending)
3. Find the first position where array becomes unsorted
4. Count number of elements that are out of place

This problem teaches fundamental array traversal and comparison logic, essential for many advanced array problems.