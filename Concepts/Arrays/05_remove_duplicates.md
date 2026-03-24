# Remove Duplicates from Array

## Problem Statement
Remove duplicate elements from an array and return only unique elements.

## What are Duplicate Elements?
Duplicate elements are values that appear more than once in an array.

## Example
```
Input:  [1, 2, 3, 4, 4, 5]
Output: [1, 2, 3, 4, 5]

Input:  [1, 1, 2, 2, 3, 3]
Output: [1, 2, 3]
```

## Approach 1: Brute Force Method

### Logic
- Create a new empty array to store unique elements
- Loop through original array
- For each element, check if it already exists in unique array
- If not present, add it to unique array

### Code Implementation
```python
def remove_duplicates_brute_force(arr):
    # Create empty array to store unique elements
    unique = []
    
    # Loop through each element in original array
    for num in arr:
        # Check if element is not already in unique array
        if num not in unique:
            # Add element to unique array
            unique.append(num)
    
    # Return array with unique elements only
    return unique

# Test the function
array = [1, 2, 3, 4, 4, 5]
print("Original:", array)
result = remove_duplicates_brute_force(array)
print("After removing duplicates:", result)
```

### Code Explanation Line by Line

| Line | Code | Explanation |
|------|------|-------------|
| 1 | `unique = []` | Create empty list to store unique elements |
| 2 | `for num in arr:` | Loop through each element in original array |
| 3 | `if num not in unique:` | Check if element is not already in unique list |
| 4 | `unique.append(num)` | Add element to unique list if not present |
| 5 | `return unique` | Return the list containing only unique elements |

### Understanding `not in` Operator
```python
# Example of how 'not in' works:
unique = [1, 2, 3]

# Check if 4 is not in unique list
if 4 not in unique:  # True, because 4 is not present
    unique.append(4)  # Add 4 to list

# Check if 2 is not in unique list  
if 2 not in unique:  # False, because 2 is already present
    unique.append(2)  # This won't execute
```

### Time Complexity: O(n²)
- **Why O(n²)?** For each element, we check if it exists in unique array
- **Checking operation** takes O(n) time in worst case
- **Total**: n elements × n checking time = O(n²)

### Space Complexity: O(n)
- We create a new array to store unique elements

## Approach 2: Optimal Method (Using Set)

### Logic
- Convert array to set (automatically removes duplicates)
- Convert set back to list
- Return the result

### Code Implementation
```python
def remove_duplicates_optimal(arr):
    # Convert to set (removes duplicates) then back to list
    return list(set(arr))

# Test the function
array = [1, 2, 3, 4, 4, 5]
print("Original:", array)
result = remove_duplicates_optimal(array)
print("After removing duplicates:", result)
```

### Understanding Set Properties
```python
# What happens when we convert list to set:
original_list = [1, 2, 3, 4, 4, 5]
converted_set = set(original_list)  # {1, 2, 3, 4, 5}
back_to_list = list(converted_set)  # [1, 2, 3, 4, 5]

# Set automatically removes duplicates!
```

### Why Sets Remove Duplicates?
- **Set Definition**: A set can only contain unique elements
- **Automatic Filtering**: When converting list to set, duplicates are automatically removed
- **Mathematical Concept**: Sets in mathematics don't allow duplicate elements

### Time Complexity: O(n)
- **Set Conversion**: O(n) - visits each element once
- **List Conversion**: O(n) - converts set back to list
- **Total**: O(n) + O(n) = O(n)

### Space Complexity: O(n)
- Creates new set and new list

## Complete Working Example
```python
def demonstrate_duplicate_removal():
    # Test cases
    test_arrays = [
        [1, 2, 3, 4, 4, 5],
        [1, 1, 2, 2, 3, 3],
        [5, 5, 5, 5],
        [1, 2, 3],  # No duplicates
        []  # Empty array
    ]
    
    print("=== Duplicate Removal Demo ===")
    
    for i, arr in enumerate(test_arrays, 1):
        print(f"\nTest Case {i}:")
        print(f"Original: {arr}")
        
        # Brute Force Method
        brute_result = remove_duplicates_brute_force(arr)
        print(f"Brute Force: {brute_result}")
        
        # Optimal Method
        optimal_result = remove_duplicates_optimal(arr)
        print(f"Optimal: {optimal_result}")

# Run the demonstration
demonstrate_duplicate_removal()
```

## Method Comparison

| Aspect | Brute Force | Optimal (Set) |
|--------|-------------|---------------|
| **Time Complexity** | O(n²) | O(n) |
| **Space Complexity** | O(n) | O(n) |
| **Code Length** | Multiple lines | Single line |
| **Readability** | Shows logic clearly | Uses Python feature |
| **Order Preservation** | Maintains original order | May change order |

## Important Note About Order
```python
# Original array
arr = [3, 1, 4, 1, 5, 9, 2, 6, 5]

# Brute force maintains order
brute_result = [3, 1, 4, 5, 9, 2, 6]  # Same order as first occurrence

# Set method may change order (sets are unordered)
set_result = [1, 2, 3, 4, 5, 6, 9]  # May be in different order
```

## Step-by-Step Trace Example

### For Array [1, 2, 3, 2, 4]:

**Brute Force Method:**
```python
unique = []  # Start with empty array

# Step 1: num = 1
# 1 not in [] → Add 1
# unique = [1]

# Step 2: num = 2  
# 2 not in [1] → Add 2
# unique = [1, 2]

# Step 3: num = 3
# 3 not in [1, 2] → Add 3  
# unique = [1, 2, 3]

# Step 4: num = 2
# 2 in [1, 2, 3] → Don't add
# unique = [1, 2, 3]

# Step 5: num = 4
# 4 not in [1, 2, 3] → Add 4
# unique = [1, 2, 3, 4]
```

**Optimal Method:**
```python
# Step 1: Convert to set
set([1, 2, 3, 2, 4]) → {1, 2, 3, 4}

# Step 2: Convert back to list  
list({1, 2, 3, 4}) → [1, 2, 3, 4]
```

## Interview Tips
1. **Explain Both Methods**: Show you know multiple approaches
2. **Discuss Trade-offs**: Time complexity vs code simplicity
3. **Mention Order**: Ask if order preservation is important
4. **Handle Edge Cases**: Empty arrays, all duplicates, no duplicates
5. **Space Consideration**: Both methods use O(n) extra space

## Common Mistakes
- **Modifying Original Array**: Always create new array for result
- **Not Handling Empty Arrays**: Check for edge cases
- **Assuming Order**: Set method doesn't guarantee order preservation
- **Wrong Complexity Analysis**: Missing the nested checking in brute force

## Practice Problems
1. Remove duplicates while maintaining original order
2. Count frequency of each element
3. Find elements that appear more than once
4. Remove duplicates in-place (modify original array)

This problem introduces the concept of sets and prepares you for more complex array manipulation problems in competitive programming.