# LeetCode 26: Remove Duplicates from Sorted Array

## Problem Statement
Given an integer array `nums` sorted in **non-decreasing order**, remove the duplicates **in-place** such that each unique element appears only once. The **relative order** of the elements should be kept the same.

Return `k` after placing the final result in the first `k` slots of `nums`.

**Important:** Do not allocate extra space for another array. You must do this by modifying the input array in-place with O(1) extra memory.

## Example
```
Input: nums = [0,0,1,1,1,2,2,3,3,4]
Output: 5, nums = [0,1,2,3,4,_,_,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums being 0, 1, 2, 3, and 4 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

## Key Constraints
- Array is already sorted
- Modify array in-place (no extra space)
- Return count of unique elements
- Elements after k don't matter

## Approach: Two Pointer Technique

### Logic
- Use two pointers: `k` (slow) and `i` (fast)
- `k` tracks position for next unique element
- `i` scans through array to find unique elements
- When unique element found, place it at position `k`

### Why This Works?
1. **First element is always unique** (k starts at 1)
2. **Compare current with previous** to find unique elements
3. **In-place replacement** saves space
4. **Sorted array** ensures duplicates are adjacent

### Code Implementation
```python
def removeDuplicates(nums):
    # Handle edge case
    if not nums:
        return 0
    
    # First element is always unique
    k = 1
    
    # Start from second element
    for i in range(1, len(nums)):
        # If current element is different from previous
        if nums[i] != nums[i - 1]:
            # Place unique element at position k
            nums[k] = nums[i]
            # Move to next position
            k += 1
    
    # Return count of unique elements
    return k

# Test the function
nums = [0, 0, 1, 1, 1, 2, 2, 3, 3, 4]
print("Before:", nums)
k = removeDuplicates(nums)
print("After:", nums[:k])  # Only first k elements matter
print("Unique count:", k)
```

### Code Explanation Line by Line

| Line | Code | Explanation |
|------|------|-------------|
| 1 | `k = 1` | First element is always unique, so k starts at 1 |
| 2 | `for i in range(1, len(nums)):` | Start from second element (index 1) |
| 3 | `if nums[i] != nums[i - 1]:` | Check if current element differs from previous |
| 4 | `nums[k] = nums[i]` | Place unique element at position k |
| 5 | `k += 1` | Move k to next position for next unique element |
| 6 | `return k` | Return count of unique elements |

## Step-by-Step Trace Example

### For Array [0, 0, 1, 1, 1, 2, 2, 3, 3, 4]:

```python
Initial: nums = [0, 0, 1, 1, 1, 2, 2, 3, 3, 4], k = 1

# Iteration 1: i = 1
# nums[1] = 0, nums[0] = 0
# 0 == 0, so no change
# nums = [0, 0, 1, 1, 1, 2, 2, 3, 3, 4], k = 1

# Iteration 2: i = 2  
# nums[2] = 1, nums[1] = 0
# 1 != 0, so unique element found
# nums[k] = nums[1] = 1
# nums = [0, 1, 1, 1, 1, 2, 2, 3, 3, 4], k = 2

# Iteration 3: i = 3
# nums[3] = 1, nums[2] = 1  
# 1 == 1, so no change
# nums = [0, 1, 1, 1, 1, 2, 2, 3, 3, 4], k = 2

# Iteration 4: i = 4
# nums[4] = 1, nums[3] = 1
# 1 == 1, so no change  
# nums = [0, 1, 1, 1, 1, 2, 2, 3, 3, 4], k = 2

# Iteration 5: i = 5
# nums[5] = 2, nums[4] = 1
# 2 != 1, so unique element found
# nums[k] = nums[2] = 2
# nums = [0, 1, 2, 1, 1, 2, 2, 3, 3, 4], k = 3

# Continue this process...
# Final: nums = [0, 1, 2, 3, 4, _, _, _, _, _], k = 5
```

## Visual Representation

```
Original: [0, 0, 1, 1, 1, 2, 2, 3, 3, 4]
           ↑     ↑           ↑     ↑     ↑
         unique unique    unique unique unique

After:    [0, 1, 2, 3, 4, _, _, _, _, _]
           ↑  ↑  ↑  ↑  ↑
         All unique elements moved to front
```

## Complete Working Example
```python
def demonstrate_remove_duplicates():
    test_cases = [
        [1, 1, 2],
        [0, 0, 1, 1, 1, 2, 2, 3, 3, 4],
        [1, 2, 3, 4, 5],  # No duplicates
        [1, 1, 1, 1, 1],  # All same
        [1]               # Single element
    ]
    
    print("=== LeetCode 26: Remove Duplicates Demo ===")
    
    for i, nums in enumerate(test_cases, 1):
        original = nums.copy()
        k = removeDuplicates(nums)
        
        print(f"\nTest Case {i}:")
        print(f"Original: {original}")
        print(f"Modified: {nums[:k]} (first {k} elements)")
        print(f"Unique count: {k}")

# Run the demonstration
demonstrate_remove_duplicates()
```

## Algorithm Analysis

### Time Complexity: O(n)
- **Single pass** through the array
- Each element visited exactly once
- No nested loops

### Space Complexity: O(1)
- **In-place modification** - no extra arrays
- Only using two variables (k and i)
- Constant extra space regardless of input size

## Key Insights

### Why Two Pointers Work?
1. **Sorted Array Property**: Duplicates are always adjacent
2. **Slow Pointer (k)**: Tracks where to place next unique element
3. **Fast Pointer (i)**: Scans to find unique elements
4. **In-place Swapping**: Overwrites duplicates with unique elements

### LeetCode Specific Points
- **Return Type**: Integer (count of unique elements)
- **Array Modification**: First k elements contain unique values
- **Don't Care About Rest**: Elements after index k are irrelevant
- **Judge System**: Only checks first k elements

## Common Mistakes
- **Starting from index 0**: First element is always unique
- **Wrong comparison**: Compare with previous element, not next
- **Not updating k**: Forgetting to increment k after placement
- **Extra space usage**: Creating new arrays instead of in-place

## Interview Tips
1. **Clarify Requirements**: Confirm in-place modification needed
2. **Explain Two Pointers**: Why this technique works for sorted arrays
3. **Handle Edge Cases**: Empty array, single element, all same
4. **Trace Through Example**: Show step-by-step execution
5. **Discuss Complexity**: O(n) time, O(1) space

## Similar LeetCode Problems
- **LeetCode 27**: Remove Element
- **LeetCode 80**: Remove Duplicates from Sorted Array II
- **LeetCode 283**: Move Zeroes
- **LeetCode 26**: Remove Duplicates from Sorted Array (this problem)

## Practice Variations
1. Remove duplicates allowing at most 2 occurrences
2. Remove specific element from array
3. Move all zeros to end while maintaining order
4. Remove duplicates from unsorted array

This problem introduces the powerful **two-pointer technique** commonly used in array problems and demonstrates **in-place array modification** - essential skills for technical interviews.