# Intersection of Two Arrays

## Problem Statement
Given two integer arrays `nums1` and `nums2`, return an array of their intersection. Each element in the result must be **unique** and you may return the result in **any order**.

## Example
```
Input: nums1 = [1, 2, 2, 1], nums2 = [2, 2]
Output: [2]

Input: nums1 = [4, 9, 5], nums2 = [9, 4, 9, 8, 4]
Output: [9, 4] or [4, 9]
```

## What is Array Intersection?
Array intersection means finding elements that are **common** in both arrays. In mathematics, intersection is represented by the overlapping area of two circles in a Venn diagram.

## Visual Representation
```
Array 1: [1, 2, 2, 1]  →  Set: {1, 2}
Array 2: [2, 2]        →  Set: {2}
Intersection: {2}      →  Result: [2]
```

## Key Requirements
- Find common elements between two arrays
- Result should contain **unique elements only**
- Order of result doesn't matter
- Handle duplicate elements properly

## Approach 1: Brute Force Method

### Logic
- For each element in first array, check if it exists in second array
- If found and not already in result, add to result
- Optimize by iterating through smaller array first

### Code Implementation
```python
def intersection_brute_force(nums1, nums2):
    result = []
    m = len(nums1)
    n = len(nums2)
    
    # Optimize: iterate through smaller array
    if m > n:
        # nums1 is larger, iterate through nums2
        for num in nums2:
            if num in nums1 and num not in result:
                result.append(num)
    else:
        # nums2 is larger, iterate through nums1
        for num in nums1:
            if num in nums2 and num not in result:
                result.append(num)
    
    return result

# Test the function
nums1 = [1, 2, 2, 1]
nums2 = [2, 2]
print("Array 1:", nums1)
print("Array 2:", nums2)
result = intersection_brute_force(nums1, nums2)
print("Intersection:", result)
```

### Code Explanation Line by Line

| Line | Code | Explanation |
|------|------|-------------|
| 1 | `result = []` | Initialize empty array to store intersection |
| 2-3 | `m = len(nums1)`, `n = len(nums2)` | Get lengths of both arrays |
| 4 | `if m > n:` | Check which array is smaller for optimization |
| 5 | `for num in nums2:` | Iterate through smaller array |
| 6 | `if num in nums1 and num not in result:` | Check if element exists in other array and not already added |
| 7 | `result.append(num)` | Add unique intersection element |

### Why Iterate Through Smaller Array?
```python
# Example: nums1 = [1,2,3,4,5,6,7,8,9,10], nums2 = [5,6]
# Better to iterate through nums2 (2 elements) than nums1 (10 elements)
# Reduces number of iterations from 10 to 2
```

### Time Complexity: O(m × n)
- **Outer loop**: O(min(m, n)) - iterate through smaller array
- **`in` operation**: O(max(m, n)) - search in larger array
- **Total**: O(min(m, n) × max(m, n)) = O(m × n)

### Space Complexity: O(min(m, n))
- Result array can have at most min(m, n) elements

## Approach 2: Optimal Method (Set Intersection)

### Logic
- Convert both arrays to sets (removes duplicates automatically)
- Use set intersection operation to find common elements
- Convert result back to list

### Code Implementation
```python
def intersection_optimal(nums1, nums2):
    # Convert arrays to sets and find intersection
    return list(set(nums1) & set(nums2))

# Alternative syntax
def intersection_optimal_alt(nums1, nums2):
    # Using intersection() method
    return list(set(nums1).intersection(set(nums2)))

# Test the function
nums1 = [1, 2, 2, 1]
nums2 = [2, 2]
print("Array 1:", nums1)
print("Array 2:", nums2)
result = intersection_optimal(nums1, nums2)
print("Intersection:", result)
```

### Understanding Set Operations
```python
# Example: nums1 = [1, 2, 2, 1], nums2 = [2, 2]

# Step 1: Convert to sets (removes duplicates)
set1 = set([1, 2, 2, 1])  # {1, 2}
set2 = set([2, 2])        # {2}

# Step 2: Find intersection
intersection = set1 & set2  # {2}

# Step 3: Convert back to list
result = list(intersection)  # [2]
```

### Set Intersection Operators
```python
# Two ways to find intersection:
# Method 1: Using & operator
result = set1 & set2

# Method 2: Using intersection() method
result = set1.intersection(set2)

# Both produce the same result
```

### Time Complexity: O(m + n)
- **Set conversion**: O(m) + O(n) - convert both arrays to sets
- **Intersection**: O(min(m, n)) - find common elements
- **List conversion**: O(intersection_size)
- **Total**: O(m + n)

### Space Complexity: O(m + n)
- Two sets created from input arrays

## Step-by-Step Trace Example

### For Arrays [4, 9, 5] and [9, 4, 9, 8, 4]:

**Set Method:**
```python
nums1 = [4, 9, 5]
nums2 = [9, 4, 9, 8, 4]

# Step 1: Convert to sets
set1 = {4, 9, 5}
set2 = {9, 4, 8}

# Step 2: Find intersection
intersection = {4, 9, 5} & {9, 4, 8} = {4, 9}

# Step 3: Convert to list
result = [4, 9]  # or [9, 4] (order may vary)
```

## Complete Working Example
```python
def demonstrate_intersection():
    test_cases = [
        ([1, 2, 2, 1], [2, 2]),
        ([4, 9, 5], [9, 4, 9, 8, 4]),
        ([1, 2, 3], [4, 5, 6]),      # No intersection
        ([1, 2, 3], [1, 2, 3]),      # Complete intersection
        ([1], [1, 1, 1]),            # Single element
        ([], [1, 2, 3])              # Empty array
    ]
    
    print("=== Array Intersection Demo ===")
    
    for i, (nums1, nums2) in enumerate(test_cases, 1):
        print(f"\nTest Case {i}:")
        print(f"Array 1: {nums1}")
        print(f"Array 2: {nums2}")
        
        # Brute Force Method
        brute_result = intersection_brute_force(nums1, nums2)
        print(f"Brute Force: {brute_result}")
        
        # Optimal Method
        optimal_result = intersection_optimal(nums1, nums2)
        print(f"Optimal: {optimal_result}")

# Run the demonstration
demonstrate_intersection()
```

## Method Comparison

| Aspect | Brute Force | Optimal (Set) |
|--------|-------------|---------------|
| **Time Complexity** | O(m × n) | O(m + n) |
| **Space Complexity** | O(min(m, n)) | O(m + n) |
| **Code Length** | Multiple lines | Single line |
| **Readability** | Clear logic | Requires set knowledge |
| **Performance** | Slow for large arrays | Fast for all sizes |

## Key Insights

### Why Sets Are Optimal?
1. **Automatic Deduplication**: Sets only store unique elements
2. **Fast Lookup**: Set membership testing is O(1) average case
3. **Built-in Operations**: Intersection operation is optimized
4. **Mathematical Concept**: Direct implementation of set theory

### Visual Comparison
```
Brute Force: Check each element manually
[1,2,2,1] vs [2,2] → Check 1 in [2,2]? No
                   → Check 2 in [2,2]? Yes, add to result
                   → Check 2 in [2,2]? Yes, but already in result
                   → Check 1 in [2,2]? No

Set Method: Mathematical intersection
{1,2} ∩ {2} = {2} → Direct result
```

## Interview Tips
1. **Clarify Requirements**: Confirm unique elements needed
2. **Discuss Both Methods**: Show brute force first, then optimize
3. **Explain Set Theory**: Why intersection works mathematically
4. **Handle Edge Cases**: Empty arrays, no intersection, complete overlap
5. **Time Complexity**: Emphasize O(m×n) vs O(m+n) improvement

## Common Mistakes
- **Not handling duplicates**: Forgetting to ensure unique results
- **Wrong complexity analysis**: Missing the nested nature of brute force
- **Set vs List confusion**: Returning set instead of list
- **Empty array handling**: Not considering edge cases

## LeetCode Connection
This is **LeetCode 349: Intersection of Two Arrays** (Easy difficulty). The set-based approach is the most elegant solution.

## Practice Variations
1. **Intersection of Two Arrays II**: Allow duplicates in result
2. **Intersection of Multiple Arrays**: Find common elements in n arrays
3. **Union of Two Arrays**: Find all unique elements from both arrays
4. **Symmetric Difference**: Elements in either array but not both

## Alternative Approaches
1. **Sorting + Two Pointers**: O((m+n)log(m+n)) time, O(1) space
2. **Hash Map**: O(m+n) time, O(min(m,n)) space
3. **Binary Search**: O(m log n) time if one array is much smaller

This problem demonstrates the power of **set operations** and shows how mathematical concepts can lead to elegant programming solutions.