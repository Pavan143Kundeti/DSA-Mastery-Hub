# Python For Loops

## What are For Loops?

**Definition:** A for loop is used for iterating over a sequence (list, tuple, dictionary, set, or string).

Python for loops work like an iterator, executing statements once for each item in a sequence.

---

## Python Loop Types

| Loop Type | Purpose |
|-----------|---------|
| **while** | Repeat while condition is true |
| **for** | Iterate over a sequence |

---

## Basic For Loop

**Definition:** Execute a set of statements once for each item in a sequence.

### Syntax
```python
for variable in sequence:
    statement
```

### Example
```python
fruits = ["apple", "banana", "cherry"]

for x in fruits:
    print(x)

# Output:
# apple
# banana
# cherry
```

**Note:** For loops don't require an indexing variable to be set beforehand.

---

## How For Loop Works

| Step | Action |
|------|--------|
| 1 | Take first item from sequence |
| 2 | Assign to variable |
| 3 | Execute code block |
| 4 | Repeat for next item |
| 5 | Stop when sequence ends |

---

## Looping Through a String

**Definition:** Strings are iterable objects containing a sequence of characters.

```python
for x in "banana":
    print(x)

# Output:
# b
# a
# n
# a
# n
# a
```


## Iterating Different Data Types

| Data Type | Example |
|-----------|---------|
| List | `for x in [1, 2, 3]:` |
| Tuple | `for x in (1, 2, 3):` |
| Set | `for x in {1, 2, 3}:` |
| String | `for x in "hello":` |
| Dictionary | `for x in {"a": 1}:` |

---

## The Break Statement

**Definition:** Stop the loop before it has looped through all items.

### Example 1: Break After Finding Item
```python
fruits = ["apple", "banana", "cherry"]

for x in fruits:
    print(x)
    if x == "banana":
        break

# Output:
# apple
# banana
```

### Example 2: Break Before Print
```python
fruits = ["apple", "banana", "cherry"]

for x in fruits:
    if x == "banana":
        break
    print(x)

# Output:
# apple
```

---

## The Continue Statement

**Definition:** Stop the current iteration and continue with the next.

```python
fruits = ["apple", "banana", "cherry"]

for x in fruits:
    if x == "banana":
        continue
    print(x)

# Output:
# apple
# cherry
```

**Note:** "banana" is skipped.

---

## Break vs Continue

| Statement | Action | Example Output |
|-----------|--------|----------------|
| `break` | Exit loop completely | apple, banana (stops) |
| `continue` | Skip current, continue loop | apple, cherry (skips banana) |


## The range() Function

**Definition:** The range() function returns a sequence of numbers, used to loop a specific number of times.

### Syntax
```python
range(stop)              # 0 to stop-1
range(start, stop)       # start to stop-1
range(start, stop, step) # start to stop-1, increment by step
```

### Basic Range Example
```python
for x in range(6):
    print(x)

# Output:
# 0
# 1
# 2
# 3
# 4
# 5
```

**Note:** `range(6)` means 0 to 5, NOT 0 to 6.

---

## Range Parameters

| Parameter | Default | Description | Example |
|-----------|---------|-------------|---------|
| start | 0 | Starting number | `range(2, 6)` starts at 2 |
| stop | Required | Ending number (not included) | `range(6)` stops before 6 |
| step | 1 | Increment value | `range(0, 10, 2)` steps by 2 |

---

## Range with Start Parameter

```python
for x in range(2, 6):
    print(x)

# Output:
# 2
# 3
# 4
# 5
```

**Note:** Starts at 2, stops before 6.

---

## Range with Step Parameter

```python
for x in range(2, 30, 3):
    print(x)

# Output:
# 2
# 5
# 8
# 11
# 14
# 17
# 20
# 23
# 26
# 29
```

**Note:** Increments by 3 each time.


## Range Examples

### Count Down
```python
for x in range(5, 0, -1):
    print(x)

# Output:
# 5
# 4
# 3
# 2
# 1
```

### Even Numbers
```python
for x in range(0, 11, 2):
    print(x)

# Output: 0, 2, 4, 6, 8, 10
```

### Odd Numbers
```python
for x in range(1, 11, 2):
    print(x)

# Output: 1, 3, 5, 7, 9
```

---

## Else in For Loop

**Definition:** The else keyword specifies a block of code to execute when the loop finishes.

### Syntax
```python
for variable in sequence:
    statement
else:
    final_statement
```

### Example
```python
for x in range(6):
    print(x)
else:
    print("Finally finished!")

# Output:
# 0
# 1
# 2
# 3
# 4
# 5
# Finally finished!
```

---

## Else with Break

**Important:** The else block will NOT execute if the loop is stopped by a break statement.

### Example: Else Does NOT Execute
```python
for x in range(6):
    if x == 3:
        break
    print(x)
else:
    print("Finally finished!")

# Output:
# 0
# 1
# 2
```

**Note:** "Finally finished!" is NOT printed because of break.


## Nested Loops

**Definition:** A loop inside another loop. The inner loop executes completely for each iteration of the outer loop.

### Syntax
```python
for outer_var in outer_sequence:
    for inner_var in inner_sequence:
        statement
```

### Example
```python
adj = ["red", "big", "tasty"]
fruits = ["apple", "banana", "cherry"]

for x in adj:
    for y in fruits:
        print(x, y)

# Output:
# red apple
# red banana
# red cherry
# big apple
# big banana
# big cherry
# tasty apple
# tasty banana
# tasty cherry
```

---

## How Nested Loops Work

| Outer Loop | Inner Loop Executes |
|------------|---------------------|
| 1st iteration | All inner iterations |
| 2nd iteration | All inner iterations |
| 3rd iteration | All inner iterations |

### Execution Flow
```
Outer: red
  Inner: apple, banana, cherry
Outer: big
  Inner: apple, banana, cherry
Outer: tasty
  Inner: apple, banana, cherry
```

---

## More Nested Loop Examples

### Multiplication Table
```python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i} x {j} = {i*j}")
    print()  # Empty line after each table

# Output:
# 1 x 1 = 1
# 1 x 2 = 2
# 1 x 3 = 3
#
# 2 x 1 = 2
# 2 x 2 = 4
# 2 x 3 = 6
# ...
```

### Pattern Printing
```python
for i in range(1, 4):
    for j in range(i):
        print("*", end="")
    print()

# Output:
# *
# **
# ***
```


## The Pass Statement

**Definition:** For loops cannot be empty. Use pass statement as a placeholder to avoid errors.

### Syntax
```python
for variable in sequence:
    pass
```

### Example
```python
for x in [0, 1, 2]:
    pass

# No error, nothing happens
```

---

## Practical For Loop Examples

### Example 1: Sum of List
```python
numbers = [1, 2, 3, 4, 5]
total = 0

for num in numbers:
    total += num

print(f"Sum: {total}")
# Output: Sum: 15
```

### Example 2: Find Maximum
```python
numbers = [3, 7, 2, 9, 1]
max_num = numbers[0]

for num in numbers:
    if num > max_num:
        max_num = num

print(f"Maximum: {max_num}")
# Output: Maximum: 9
```

### Example 3: Count Vowels
```python
text = "hello world"
vowels = "aeiou"
count = 0

for char in text:
    if char in vowels:
        count += 1

print(f"Vowels: {count}")
# Output: Vowels: 3
```

### Example 4: List Comprehension Alternative
```python
# Using for loop
squares = []
for x in range(5):
    squares.append(x ** 2)

print(squares)
# Output: [0, 1, 4, 9, 16]
```

### Example 5: Dictionary Iteration
```python
person = {"name": "John", "age": 30, "city": "New York"}

# Iterate keys
for key in person:
    print(key)

# Iterate values
for value in person.values():
    print(value)

# Iterate key-value pairs
for key, value in person.items():
    print(f"{key}: {value}")
```


## Looping with Index - enumerate()

**Definition:** Use enumerate() to get both index and value while looping.

```python
fruits = ["apple", "banana", "cherry"]

for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")

# Output:
# 0: apple
# 1: banana
# 2: cherry
```

### Start Index from 1
```python
for index, fruit in enumerate(fruits, start=1):
    print(f"{index}: {fruit}")

# Output:
# 1: apple
# 2: banana
# 3: cherry
```

---

## Looping Multiple Lists - zip()

**Definition:** Use zip() to loop through multiple lists simultaneously.

```python
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]

for name, age in zip(names, ages):
    print(f"{name} is {age} years old")

# Output:
# Alice is 25 years old
# Bob is 30 years old
# Charlie is 35 years old
```

---

## For Loop Control Flow

| Statement | Purpose | Example |
|-----------|---------|---------|
| `for` | Start loop | `for x in range(5):` |
| `break` | Exit loop | `if x == 3: break` |
| `continue` | Skip iteration | `if x == 2: continue` |
| `else` | After loop ends | `else: print("Done")` |
| `pass` | Placeholder | `pass` |

---

## Common For Loop Patterns

### Pattern 1: Iterate List
```python
for item in list:
    print(item)
```

### Pattern 2: Iterate Range
```python
for i in range(10):
    print(i)
```

### Pattern 3: Iterate with Index
```python
for i, item in enumerate(list):
    print(i, item)
```

### Pattern 4: Iterate Dictionary
```python
for key, value in dict.items():
    print(key, value)
```

### Pattern 5: Nested Loop
```python
for i in range(3):
    for j in range(3):
        print(i, j)
```


## For vs While Loop

| Feature | For Loop | While Loop |
|---------|----------|------------|
| **Use Case** | Known iterations | Unknown iterations |
| **Syntax** | `for x in sequence:` | `while condition:` |
| **Iteration** | Automatic | Manual increment |
| **Best For** | Sequences, ranges | Condition-based |
| **Index Variable** | Not required | Required |

### Same Task - Different Loops

```python
# Using for loop
for i in range(5):
    print(i)

# Using while loop
i = 0
while i < 5:
    print(i)
    i += 1
```

---

## Common Mistakes

### Mistake 1: Modifying List While Iterating
```python
# Wrong - can cause issues
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    if num % 2 == 0:
        numbers.remove(num)  # Don't modify while iterating

# Correct - iterate over copy
numbers = [1, 2, 3, 4, 5]
for num in numbers[:]:
    if num % 2 == 0:
        numbers.remove(num)
```

### Mistake 2: Wrong Range
```python
# Wrong - range(5) gives 0-4, not 1-5
for i in range(5):
    print(i)  # Prints 0, 1, 2, 3, 4

# Correct - for 1-5
for i in range(1, 6):
    print(i)  # Prints 1, 2, 3, 4, 5
```

### Mistake 3: Forgetting Indentation
```python
# Wrong
for i in range(3):
print(i)  # IndentationError

# Correct
for i in range(3):
    print(i)
```

---

## Quick Reference Summary

### Basic For Loop
```python
for item in sequence:
    statement
```

### With Range
```python
for i in range(start, stop, step):
    statement
```

### With Break
```python
for item in sequence:
    if condition:
        break
```

### With Continue
```python
for item in sequence:
    if condition:
        continue
```

### With Else
```python
for item in sequence:
    statement
else:
    final_statement
```

### Nested Loop
```python
for i in outer:
    for j in inner:
        statement
```


## Key Takeaways

### ✅ Remember
- **For loop** iterates over sequences (list, tuple, string, etc.)
- **No index variable** needed (unlike while loop)
- **range()** creates number sequences: range(start, stop, step)
- **range(6)** gives 0-5, NOT 0-6
- **break** exits loop completely
- **continue** skips current iteration
- **else** executes when loop ends normally (not with break)
- **Nested loops**: Inner loop completes for each outer iteration
- **pass** is placeholder for empty loops
- **enumerate()** gives index and value
- **zip()** loops multiple sequences together

### 🎯 Interview Important
- Difference between for and while loops
- How range() works (start, stop, step)
- When else block executes (not with break)
- Nested loop execution order
- enumerate() for index access
- zip() for parallel iteration
- Don't modify list while iterating over it
- Time complexity of nested loops: O(n²)

---

## When to Use For Loop

| Use For Loop When | Example |
|-------------------|---------|
| Iterating sequences | Lists, tuples, strings |
| Known number of iterations | range(10) |
| Processing each item | Calculate sum, find max |
| Nested iterations | Multiplication tables |
| Dictionary iteration | Loop through keys/values |

---

**Master for loops to efficiently iterate through sequences and collections in Python!**
