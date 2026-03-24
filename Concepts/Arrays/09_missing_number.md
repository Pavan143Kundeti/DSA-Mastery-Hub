# Missing Number

## Problem Statement
Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.

## Example
```
Input: nums = [3, 0, 1]
Output: 2
Explanation: n = 3 since there are 3 numbers, so all numbers are in the range [0, 3]. 2 is the missing number in the range since it does not appear in nums.

Input: nums = [0, 1]
Output: 2
Explanation: n = 2 since there are 2 numbers, so all numbers are in the range [0, 2]. 2 is the missing number in the range since it does not appear in nums.

Input: nums = [9, 6, 4, 2, 3, 5, 7, 0, 1]
Output: 8
Explanation: n = 9 since there are 9 numbers, so all numbers are in the range [0, 9]. 8 is the missing number in the range since it does not appear in nums.
```

## Key Understanding
- Array has `n` elements
- Numbers should be in range `[0, n]` (total n+1 numbers possible)
- Exactly one number is missing from this range
- Find that missing number

## Approach 1: Brute Force Method

### Logic
- Check each number from 0 to n
- If any number is not present in array, return it
- Use Python's `not in` operator for checking

### Code Implementation
```python
def missing_number_brute_force(nums):
    n = len(nums)
    
    # Check each number from 0 to n
    for i in range(n + 1):
        if i not in nums:
            return i
    
    # This should never be reached
    return -1

# Test the function
nums = [3, 0, 1]
print("Array:", nums)
result = missing_number_brute_force(nums)
print("Missing number:", result)
```

### Code Explanation Line by Line

| Line | Code | Explanation |
|------|------|-------------|
| 1 | `n = len(nums)` | Get array length (number of elements present) |
| 2 | `for i in range(n + 1):` | Check numbers from 0 to n (inclusive) |
| 3 | `if i not in nums:` | Check if current number is missing from array |
| 4 | `return i` | Return the missing number |

### Why range(n + 1)?
```python
# Example: nums = [3, 0, 1]
# n = len(nums) = 3
# Range should be [0, 1, 2, 3] (total 4 numbers)
# So we need range(n + 1) = range(4) = [0, 1, 2, 3]
```

### Time Complexity: O(n²)
- **Outer loop**: O(n) - checks n+1 numbers
- **`not in` operation**: O(n) - searches through array
- **Total**: O(n) × O(n) = O(n²)

### Space Complexity: O(1)
- No extra space used

## Approach 2: Optimal Method (Mathematical Formula)

### Logic
- Calculate expected sum of numbers from 0 to n
- Calculate actual sum of given array
- Difference gives the missing number

### Mathematical Formula
```
Sum of first n natural numbers = n × (n + 1) / 2
But our range is [0, n], so sum = 0 + 1 + 2 + ... + n = n × (n + 1) / 2
```

### Code Implementation
```python
def missing_number_optimal(nums):
    n = len(nums)
    
    # Calculate expected sum using formula
    expected_sum = n * (n + 1) // 2
    
    # Calculate actual sum of array
    actual_sum = sum(nums)
    
    # Missing number is the difference
    return expected_sum - actual_sum

# Test the function
nums = [3, 0, 1]
print("Array:", nums)
result = missing_number_optimal(nums)
print("Missing number:", result)
```

### Code Explanation Line by Line

| Line | Code | Explanation |
|------|------|-------------|
| 1 | `n = len(nums)` | Get array length |
| 2 | `expected_sum = n * (n + 1) // 2` | Calculate sum of [0, 1, 2, ..., n] |
| 3 | `actual_sum = sum(nums)` | Calculate sum of given array |
| 4 | `return expected_sum - actual_sum` | Missing number is the difference |

### Understanding the Formula
```python
# For nums = [3, 0, 1], n = 3
# Expected range: [0, 1, 2, 3]
# Expected sum = 0 + 1 + 2 + 3 = 6
# Using formula: 3 × (3 + 1) // 2 = 3 × 4 // 2 = 6

# Actual sum = 3 + 0 + 1 = 4
# Missing number = 6 - 4 = 2
```

### Why // instead of /?
```python
# Using / gives float result
# 3 * 4 / 2 = 6.0 (float)

# Using // gives integer result  
# 3 * 4 // 2 = 6 (integer)

# We need integer for array indexing
```

### Time Complexity: O(n)
- **Formula calculation**: O(1)
- **sum() function**: O(n) - iterates through array once
- **Total**: O(n)

### Space Complexity: O(1)
- Only using a few variables

## Step-by-Step Trace Example

### For Array [9, 6, 4, 2, 3, 5, 7, 0, 1]:

**Mathematical Method:**
```python
nums = [9, 6, 4, 2, 3, 5, 7, 0, 1]
n = len(nums) = 9

# Expected sum for range [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
expected_sum = 9 × (9 + 1) // 2 = 9 × 10 // 2 = 45

# Actual sum of given array
actual_sum = 9 + 6 + 4 + 2 + 3 + 5 + 7 + 0 + 1 = 37

# Missing number
missing = 45 - 37 = 8
```

## Complete Working Example
```python
def demonstrate_missing_number():
    test_cases = [
        [3, 0, 1],
        [0, 1],
        [9, 6, 4, 2, 3, 5, 7, 0, 1],
        [1, 2, 3, 4, 5],  # Missing 0
        [0, 1, 2, 3, 4]   # Missing 5 (last number)
    ]
    
    print("=== Missing Number Demo ===")
    
    for i, nums in enumerate(test_cases, 1):
        print(f"\nTest Case {i}:")
        print(f"Array: {nums}")
        print(f"Range: [0, {len(nums)}]")
        
        # Brute Force Method
        brute_result = missing_number_brute_force(nums)
        print(f"Brute Force: {brute_result}")
        
        # Optimal Method
        optimal_result = missing_number_optimal(nums)
        print(f"Optimal: {optimal_result}")

# Run the demonstration
demonstrate_missing_number()
```

## Method Comparison

| Aspect | Brute Force | Optimal (Mathematical) |
|--------|-------------|----------------------|
| **Time Complexity** | O(n²) | O(n) |
| **Space Complexity** | O(1) | O(1) |
| **Approach** | Search-based | Formula-based |
| **Code Simplicity** | Simple logic | Requires math knowledge |
| **Performance** | Slow for large arrays | Fast for all sizes |

## Key Insights

### Why Mathematical Approach Works?
1. **Complete Range**: We know exactly what numbers should be present
2. **Sum Property**: Sum of arithmetic sequence has a formula
3. **Missing Element**: Difference between expected and actual sum
4. **Single Missing**: Problem guarantees exactly one number is missing

### Visual Representation
```
Expected: [0, 1, 2, 3] → Sum = 6
Actual:   [3, 0, 1]    → Sum = 4
Missing:  2            → Difference = 6 - 4 = 2
```

## Interview Tips
1. **Clarify Range**: Confirm the range is [0, n]
2. **Explain Both Methods**: Show brute force first, then optimize
3. **Mathematical Insight**: Explain the sum formula
4. **Handle Edge Cases**: Single element, missing first/last number
5. **Complexity Analysis**: Emphasize O(n²) vs O(n) improvement

## Common Mistakes
- **Wrong range**: Using [1, n] instead of [0, n]
- **Off-by-one errors**: Not including n in the range
- **Float division**: Using / instead of // in Python
- **Assuming sorted**: Array can be in any order

## Alternative Approaches
1. **Sorting + Linear Search**: O(n log n) time
2. **Hash Set**: O(n) time, O(n) space
3. **XOR Approach**: O(n) time, O(1) space (bit manipulation)
4. **Mathematical**: O(n) time, O(1) space (shown above)

## LeetCode Connection
This is **LeetCode 268: Missing Number** (Easy difficulty). The mathematical approach is the most elegant solution.

## Practice Variations
1. Find missing number in range [1, n]
2. Find two missing numbers
3. Find missing number in arithmetic progression
4. Find missing number with duplicates allowed

This problem demonstrates how **mathematical insights** can dramatically improve algorithm efficiency and introduces the concept of **sum-based problem solving**.