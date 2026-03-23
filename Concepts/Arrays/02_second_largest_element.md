# Find Second Largest Element in Array

## Problem Statement
Given an array of numbers, find the second largest element.

**Example**: `[1, 2, 3, 4, 5, 7, 8]` → Answer: `7`

---

## Approach 1: Brute Force Method (Sorting)

### Code Implementation
```python
def brute_force_second_largest(arr):
    # Check if array has at least 2 elements
    if len(arr) < 2:
        return "Need more numbers"
    
    # Sort array in descending order
    sorted_arr = sorted(arr, reverse=True)
    
    # Return second element (index 1)
    return sorted_arr[1]

# Test the function
array = [1, 2, 3, 4, 5, 7, 8]
result = brute_force_second_largest(array)
print("Second largest:", result)  # Output: 7
```

### How Brute Force Works
1. **Sort** the array in descending order: `[8, 7, 5, 4, 3, 2, 1]`
2. **Access** element at index 1: `7`
3. **Return** the second largest element

### Complexity Analysis
- **Time Complexity**: O(n log n) - Due to sorting operation
- **Space Complexity**: O(n) - For creating sorted array

---

## Approach 2: Optimal Method (Single Pass)

### Code Implementation
```python
def optimal_second_largest(arr):
    # Check if array has at least 2 elements
    if len(arr) < 2:
        return "Need more numbers"
    
    # Initialize with negative infinity
    largest = float('-inf')
    second_largest = float('-inf')
    
    # Single pass through array
    for num in arr:
        if num > largest:
            # Update both largest and second largest
            second_largest = largest
            largest = num
        elif num > second_largest and num != largest:
            # Update only second largest
            second_largest = num
    
    # Check if second largest was found
    if second_largest != float('-inf'):
        return second_largest
    else:
        return "Not found"

# Test the function
array = [1, 2, 3, 4, 5, 7, 8]
result = optimal_second_largest(array)
print("Second largest:", result)  # Output: 7
```

### Step-by-Step Execution

Let's trace through `[1, 2, 3, 4, 5, 7, 8]`:

| Step | Current num | largest | second_largest | Condition | Action |
|------|-------------|---------|----------------|-----------|---------|
| Initial | - | -∞ | -∞ | - | Start values |
| 1 | 1 | -∞ | -∞ | 1 > -∞? **Yes** | second_largest = -∞, largest = 1 |
| 2 | 2 | 1 | -∞ | 2 > 1? **Yes** | second_largest = 1, largest = 2 |
| 3 | 3 | 2 | 1 | 3 > 2? **Yes** | second_largest = 2, largest = 3 |
| 4 | 4 | 3 | 2 | 4 > 3? **Yes** | second_largest = 3, largest = 4 |
| 5 | 5 | 4 | 3 | 5 > 4? **Yes** | second_largest = 4, largest = 5 |
| 6 | 7 | 5 | 4 | 7 > 5? **Yes** | second_largest = 5, largest = 7 |
| 7 | 8 | 7 | 5 | 8 > 7? **Yes** | second_largest = 7, largest = 8 |

**Final Result**: second_largest = 7

### Logic Breakdown

#### Condition 1: New Largest Found
```python
if num > largest:
    second_largest = largest  # Save old largest as second largest
    largest = num            # Update largest with new number
```

**Example Scenario**:
- Current: largest = 7, second_largest = 5
- New number: 8
- Result: largest = 8, second_largest = 7

#### Condition 2: New Second Largest Found
```python
elif num > second_largest and num != largest:
    second_largest = num     # Update only second largest
```

**When this works**:
- Number is bigger than current second_largest
- Number is smaller than current largest
- Number is not equal to largest (handles duplicates)

### Why Use `float('-inf')`?

| Approach | Pros | Cons |
|----------|------|------|
| `0` or random number | Simple | May not work with negative arrays |
| `float('-inf')` | ✅ Works with any numbers<br>✅ Memory optimized<br>✅ Safe comparison | Slightly complex syntax |

---

## Edge Cases & Testing

### Test Case 1: Insufficient Elements
```python
array = [5]
result = optimal_second_largest(array)
print(result)  # Output: "Need more numbers"
```

### Test Case 2: All Same Elements
```python
array = [5, 5, 5, 5]
result = optimal_second_largest(array)
print(result)  # Output: "Not found"
```

### Test Case 3: Two Different Elements
```python
array = [3, 7]
result = optimal_second_largest(array)
print(result)  # Output: 3
```

### Test Case 4: Negative Numbers
```python
array = [-1, -5, -3, -2]
result = optimal_second_largest(array)
print(result)  # Output: -2
```

---

## Comparison: Brute Force vs Optimal

| Aspect | Brute Force | Optimal |
|--------|-------------|---------|
| **Time Complexity** | O(n log n) | O(n) |
| **Space Complexity** | O(n) | O(1) |
| **Code Length** | Shorter (3-4 lines) | Longer (15+ lines) |
| **Readability** | Very easy | Moderate |
| **Performance** | Slower for large arrays | Much faster |
| **Memory Usage** | Uses extra space | Constant space |
| **Best Use Case** | Small arrays, quick prototyping | Large arrays, production code |

---

## Key Learning Points

### 1. Time Complexity Analysis
- **Sorting operations** are typically O(n log n)
- **Single loop** operations are O(n)
- Always identify the **most expensive operation**

### 2. Space Optimization
- Brute force creates a new sorted array
- Optimal approach uses only two variables
- **Constant space** is always preferred when possible

### 3. Edge Case Handling
- Always check for **minimum required elements**
- Handle **duplicate values** appropriately
- Provide **meaningful error messages**

### 4. Variable Initialization
- Use appropriate starting values
- `float('-inf')` is safer than arbitrary numbers
- Consider the **range of possible inputs**

---

## Practice Exercises

1. **Modify the code** to find the third largest element
2. **Handle duplicates** by returning the second unique largest
3. **Implement** without using `float('-inf')`
4. **Test performance** with arrays of different sizes

---

## Interview Tips

1. **Start with brute force** - shows you understand the problem
2. **Explain the approach** before coding
3. **Discuss time complexity** of both solutions
4. **Handle edge cases** proactively
5. **Test with examples** to verify correctness

---

**Time Complexity**: O(n) for optimal approach
**Space Complexity**: O(1) for optimal approach

This problem teaches fundamental array traversal patterns that appear in many other algorithms!