# Move Zeros to End

## Problem Statement
Given an integer array `nums`, move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

**Note:** You must do this **in-place** without making a copy of the array.

## Example
```
Input: nums = [0, 1, 0, 3, 12]
Output: [1, 3, 12, 0, 0]

Input: nums = [0, 0, 1, 0, 3, 0, 12]
Output: [1, 3, 12, 0, 0, 0, 0]
```

## Key Requirements
- Move all zeros to the end
- Maintain order of non-zero elements
- Modify array in-place (no extra space)
- Preserve original array structure

## Approach 1: Brute Force Method

### Logic
- Create separate arrays for non-zero elements and count zeros
- Combine non-zero elements with required number of zeros
- Update original array with result

### Code Implementation
```python
def move_zeros_brute_force(nums):
    n = len(nums)
    
    # Collect all non-zero elements
    non_zeros = []
    for num in nums:
        if num != 0:
            non_zeros.append(num)
    
    # Count zeros needed
    zeros_count = n - len(non_zeros)
    
    # Create result: non-zeros + zeros
    result = non_zeros + [0] * zeros_count
    
    # Update original array
    for i in range(n):
        nums[i] = result[i]
    
    return nums

# Test the function
nums = [0, 1, 0, 3, 12]
print("Before:", nums)
result = move_zeros_brute_force(nums.copy())
print("After:", result)
```

### Code Explanation Line by Line

| Line | Code | Explanation |
|------|------|-------------|
| 1 | `n = len(nums)` | Store array length for later use |
| 2 | `for num in nums:` | Iterate through each element |
| 3 | `if num != 0:` | Check if element is not zero |
| 4 | `non_zeros.append(num)` | Add non-zero elements to separate array |
| 5 | `zeros_count = n - len(non_zeros)` | Calculate how many zeros needed |
| 6 | `result = non_zeros + [0] * zeros_count` | Combine non-zeros with zeros |
| 7 | `nums[i] = result[i]` | Update original array in-place |

### Understanding Array Concatenation
```python
# Example: nums = [0, 1, 0, 3, 12]
# non_zeros = [1, 3, 12] (length = 3)
# zeros_count = 5 - 3 = 2
# [0] * zeros_count = [0] * 2 = [0, 0]
# result = [1, 3, 12] + [0, 0] = [1, 3, 12, 0, 0]
```

### Time Complexity: O(n)
- **First loop**: O(n) - collect non-zero elements
- **Second loop**: O(n) - update original array
- **Total**: O(n) + O(n) = O(n)

### Space Complexity: O(n)
- Creates extra arrays for non-zero elements and result

## Approach 2: Optimal Method (Two Pointer Technique)

### Logic
- Use two pointers: `pointer` (slow) and `i` (fast)
- `pointer` tracks position for next non-zero element
- `i` scans through array to find non-zero elements
- When non-zero found, swap with element at `pointer` position

### Code Implementation
```python
def move_zeros_optimal(nums):
    # Pointer for non-zero elements position
    pointer = 0
    
    # Scan through array
    for i in range(len(nums)):
        # If current element is not zero
        if nums[i] != 0:
            # Swap elements
            nums[pointer], nums[i] = nums[i], nums[pointer]
            # Move pointer to next position
            pointer += 1
    
    return nums

# Test the function
nums = [0, 1, 0, 3, 12]
print("Before:", nums)
result = move_zeros_optimal(nums.copy())
print("After:", result)
```

### Code Explanation Line by Line

| Line | Code | Explanation |
|------|------|-------------|
| 1 | `pointer = 0` | Initialize pointer for non-zero elements |
| 2 | `for i in range(len(nums)):` | Scan through entire array |
| 3 | `if nums[i] != 0:` | Check if current element is non-zero |
| 4 | `nums[pointer], nums[i] = nums[i], nums[pointer]` | Swap elements using tuple unpacking |
| 5 | `pointer += 1` | Move pointer to next position |

### Understanding Two Pointer Technique
```python
# Example: nums = [0, 1, 0, 3, 12]
# pointer = 0, i scans from 0 to 4

# i=0: nums[0]=0, skip (no swap)
# pointer=0, nums=[0, 1, 0, 3, 12]

# i=1: nums[1]=1, non-zero found
# Swap nums[0] with nums[1]
# pointer=1, nums=[1, 0, 0, 3, 12]

# i=2: nums[2]=0, skip (no swap)  
# pointer=1, nums=[1, 0, 0, 3, 12]

# i=3: nums[3]=3, non-zero found
# Swap nums[1] with nums[3]
# pointer=2, nums=[1, 3, 0, 0, 12]

# i=4: nums[4]=12, non-zero found
# Swap nums[2] with nums[4]
# pointer=3, nums=[1, 3, 12, 0, 0]
```

### Time Complexity: O(n)
- **Single pass** through the array
- Each element visited exactly once

### Space Complexity: O(1)
- **In-place modification** - no extra arrays
- Only using two variables (pointer and i)

## Step-by-Step Trace Example

### For Array [0, 1, 0, 3, 12]:

**Two Pointer Method:**
```python
Initial: nums = [0, 1, 0, 3, 12], pointer = 0

# Step 1: i = 0
# nums[0] = 0, skip
# nums = [0, 1, 0, 3, 12], pointer = 0

# Step 2: i = 1
# nums[1] = 1 ≠ 0, swap nums[0] ↔ nums[1]
# nums = [1, 0, 0, 3, 12], pointer = 1

# Step 3: i = 2
# nums[2] = 0, skip
# nums = [1, 0, 0, 3, 12], pointer = 1

# Step 4: i = 3
# nums[3] = 3 ≠ 0, swap nums[1] ↔ nums[3]
# nums = [1, 3, 0, 0, 12], pointer = 2

# Step 5: i = 4
# nums[4] = 12 ≠ 0, swap nums[2] ↔ nums[4]
# nums = [1, 3, 12, 0, 0], pointer = 3

Final: [1, 3, 12, 0, 0]
```

## Complete Working Example
```python
def demonstrate_move_zeros():
    test_cases = [
        [0, 1, 0, 3, 12],
        [0, 0, 1, 0, 3, 0, 12],
        [1, 2, 3, 4, 5],  # No zeros
        [0, 0, 0, 0, 0],  # All zeros
        [1],              # Single element
        []                # Empty array
    ]
    
    print("=== Move Zeros to End Demo ===")
    
    for i, nums in enumerate(test_cases, 1):
        if not nums:
            print(f"\nTest Case {i}: Empty array")
            continue
            
        print(f"\nTest Case {i}:")
        print(f"Original: {nums}")
        
        # Brute Force Method
        brute_result = move_zeros_brute_force(nums.copy())
        print(f"Brute Force: {brute_result}")
        
        # Optimal Method
        optimal_result = move_zeros_optimal(nums.copy())
        print(f"Optimal: {optimal_result}")

# Run the demonstration
demonstrate_move_zeros()
```

## Method Comparison

| Aspect | Brute Force | Optimal (Two Pointer) |
|--------|-------------|----------------------|
| **Time Complexity** | O(n) | O(n) |
| **Space Complexity** | O(n) | O(1) |
| **Extra Arrays** | Yes | No |
| **In-place Modification** | Yes (final step) | Yes (throughout) |
| **Code Complexity** | Multiple steps | Single loop |
| **Memory Efficient** | No | Yes |

## Key Insights

### Why Two Pointers Work?
1. **Slow Pointer (pointer)**: Tracks position for next non-zero element
2. **Fast Pointer (i)**: Scans array to find non-zero elements
3. **Swapping Strategy**: Places non-zeros at front, zeros naturally move to end
4. **Order Preservation**: Relative order of non-zeros maintained

### Visual Representation
```
Before: [0, 1, 0, 3, 12]
         ↑              
      pointer=0

After:  [1, 3, 12, 0, 0]
                  ↑
               pointer=3 (stopped here)
```

## Interview Tips
1. **Clarify Requirements**: Confirm in-place modification needed
2. **Explain Two Pointers**: Why this technique is optimal
3. **Handle Edge Cases**: All zeros, no zeros, empty array
4. **Trace Through Example**: Show step-by-step swapping
5. **Discuss Space Optimization**: O(1) vs O(n) space

## Common Mistakes
- **Not maintaining order**: Losing relative order of non-zeros
- **Extra space usage**: Creating unnecessary arrays
- **Wrong pointer logic**: Not updating pointer correctly
- **Boundary conditions**: Not handling edge cases

## LeetCode Connection
This problem appears as **LeetCode 283: Move Zeroes** (Easy difficulty). The optimal solution uses the exact two-pointer technique shown here.

## Practice Variations
1. Move all negative numbers to end
2. Move all even numbers to beginning
3. Segregate 0s and 1s in binary array
4. Move all duplicates to end while preserving order

This problem teaches the fundamental **two-pointer technique** and demonstrates **in-place array manipulation** - essential skills for array problems in competitive programming.