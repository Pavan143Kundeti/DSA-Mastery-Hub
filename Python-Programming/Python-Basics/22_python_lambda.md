# Python Lambda Functions

## What is a Lambda Function?

**Definition:** A lambda function is a small anonymous function that can take any number of arguments but can only have one expression.

### Syntax
```python
lambda arguments : expression
```

The expression is executed and the result is returned.

---

## Basic Lambda Examples

### Single Argument
```python
x = lambda a : a + 10
print(x(5))
# Output: 15
```

### Multiple Arguments
```python
x = lambda a, b : a * b
print(x(5, 6))
# Output: 30
```

### Three Arguments
```python
x = lambda a, b, c : a + b + c
print(x(5, 6, 2))
# Output: 13
```

---

## Lambda vs Regular Function

| Feature | Regular Function | Lambda Function |
|---------|------------------|-----------------|
| Keyword | `def` | `lambda` |
| Name | Required | Anonymous |
| Statements | Multiple | Single expression |
| Return | Explicit `return` | Implicit return |
| Use case | Complex logic | Simple operations |

### Same Function - Different Syntax

```python
# Regular function
def add_ten(a):
    return a + 10

# Lambda function
add_ten = lambda a : a + 10
```


## Why Use Lambda Functions?

Lambda functions are powerful when used as anonymous functions inside other functions.

### Example: Function Factory
```python
def myfunc(n):
    return lambda a : a * n
```

### Creating a Doubler Function
```python
def myfunc(n):
    return lambda a : a * n

mydoubler = myfunc(2)
print(mydoubler(11))
# Output: 22
```

### Creating a Tripler Function
```python
def myfunc(n):
    return lambda a : a * n

mytripler = myfunc(3)
print(mytripler(11))
# Output: 33
```

### Both Functions Together
```python
def myfunc(n):
    return lambda a : a * n

mydoubler = myfunc(2)
mytripler = myfunc(3)

print(mydoubler(11))  # Output: 22
print(mytripler(11))  # Output: 33
```

**Use Case:** When an anonymous function is required for a short period of time.

---

## Lambda with Built-in Functions

Lambda functions are commonly used with `map()`, `filter()`, and `sorted()`.

### Using Lambda with map()

**Definition:** `map()` applies a function to every item in an iterable.

```python
numbers = [1, 2, 3, 4, 5]
doubled = list(map(lambda x: x * 2, numbers))
print(doubled)
# Output: [2, 4, 6, 8, 10]
```

### More map() Examples
```python
# Square all numbers
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))
print(squared)
# Output: [1, 4, 9, 16, 25]

# Convert to uppercase
words = ["hello", "world", "python"]
uppercase = list(map(lambda x: x.upper(), words))
print(uppercase)
# Output: ['HELLO', 'WORLD', 'PYTHON']
```

---

## Using Lambda with filter()

**Definition:** `filter()` creates a list of items for which a function returns True.

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8]
odd_numbers = list(filter(lambda x: x % 2 != 0, numbers))
print(odd_numbers)
# Output: [1, 3, 5, 7]
```

### More filter() Examples
```python
# Filter even numbers
numbers = [1, 2, 3, 4, 5, 6, 7, 8]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)
# Output: [2, 4, 6, 8]

# Filter numbers greater than 5
numbers = [1, 3, 5, 7, 9, 11]
greater_than_5 = list(filter(lambda x: x > 5, numbers))
print(greater_than_5)
# Output: [7, 9, 11]
```


## Using Lambda with sorted()

**Definition:** `sorted()` can use a lambda as a key for custom sorting.

### Sort by Second Element
```python
students = [("Emil", 25), ("Tobias", 22), ("Linus", 28)]
sorted_students = sorted(students, key=lambda x: x[1])
print(sorted_students)
# Output: [('Tobias', 22), ('Emil', 25), ('Linus', 28)]
```

### Sort Strings by Length
```python
words = ["apple", "pie", "banana", "cherry"]
sorted_words = sorted(words, key=lambda x: len(x))
print(sorted_words)
# Output: ['pie', 'apple', 'banana', 'cherry']
```

### Sort Dictionary by Value
```python
scores = {"Alice": 85, "Bob": 92, "Charlie": 78}
sorted_scores = sorted(scores.items(), key=lambda x: x[1])
print(sorted_scores)
# Output: [('Charlie', 78), ('Alice', 85), ('Bob', 92)]
```

---

## Practical Lambda Examples

### Example 1: Temperature Conversion
```python
celsius_to_fahrenheit = lambda c: (c * 9/5) + 32
print(celsius_to_fahrenheit(25))
# Output: 77.0
```

### Example 2: Check Even/Odd
```python
is_even = lambda x: x % 2 == 0
print(is_even(4))   # Output: True
print(is_even(7))   # Output: False
```

### Example 3: Find Maximum
```python
max_of_two = lambda a, b: a if a > b else b
print(max_of_two(10, 20))
# Output: 20
```

### Example 4: String Operations
```python
reverse_string = lambda s: s[::-1]
print(reverse_string("hello"))
# Output: olleh
```

### Example 5: Calculate Area
```python
rectangle_area = lambda length, width: length * width
print(rectangle_area(5, 3))
# Output: 15
```

---

## Lambda with Multiple Operations

### Conditional Lambda
```python
# Check if number is positive, negative, or zero
check_number = lambda x: "Positive" if x > 0 else ("Negative" if x < 0 else "Zero")
print(check_number(5))    # Output: Positive
print(check_number(-3))   # Output: Negative
print(check_number(0))    # Output: Zero
```

### Lambda with String Formatting
```python
format_name = lambda first, last: f"{first.capitalize()} {last.capitalize()}"
print(format_name("john", "doe"))
# Output: John Doe
```


## Common Use Cases

| Use Case | Example |
|----------|---------|
| Simple calculations | `lambda x: x * 2` |
| Filtering data | `filter(lambda x: x > 0, numbers)` |
| Mapping transformations | `map(lambda x: x.upper(), words)` |
| Custom sorting | `sorted(data, key=lambda x: x[1])` |
| Callback functions | `button.click(lambda: print("Clicked"))` |

---

## Lambda Limitations

| Limitation | Description |
|------------|-------------|
| Single expression | Can't have multiple statements |
| No documentation | Can't add docstrings |
| Less readable | Complex lambdas are hard to understand |
| Debugging | Harder to debug than named functions |

### When NOT to Use Lambda

```python
# Bad - Too complex for lambda
result = lambda x: x * 2 if x > 0 else x * -1 if x < 0 else 0

# Good - Use regular function
def process_number(x):
    if x > 0:
        return x * 2
    elif x < 0:
        return x * -1
    else:
        return 0
```

---

## Quick Reference

### Basic Syntax
```python
lambda arguments : expression
```

### Common Patterns
```python
# Single argument
lambda x: x * 2

# Multiple arguments
lambda x, y: x + y

# With condition
lambda x: "Even" if x % 2 == 0 else "Odd"

# With map
map(lambda x: x * 2, list)

# With filter
filter(lambda x: x > 0, list)

# With sorted
sorted(list, key=lambda x: x[1])
```

---

## Key Takeaways

### ✅ Remember
- **Lambda** creates anonymous functions
- **Single expression** only (no multiple statements)
- **Implicit return** (no return keyword needed)
- **Any number of arguments** but one expression
- **Commonly used** with map(), filter(), sorted()
- **Short-lived** functions for temporary use
- **Less readable** for complex operations
- **No docstrings** or function names

### 🎯 Interview Important
- Difference between lambda and regular functions
- When to use lambda vs def
- Lambda with map(), filter(), sorted()
- Lambda limitations (single expression)
- Lambda in function factories
- Lambda for callbacks
- Readability concerns with complex lambdas

---

**Use lambda functions for simple, short-lived operations where a full function definition would be overkill!**

---

# Python Recursion

## What is Recursion?

**Definition:** Recursion is when a function calls itself.

### Basic Example
```python
def countdown(n):
    if n <= 0:
        print("Done!")
    else:
        print(n)
        countdown(n - 1)

countdown(5)
# Output: 5, 4, 3, 2, 1, Done!
```

---

## Base Case and Recursive Case

| Component | Description | Required? |
|-----------|-------------|-----------|
| **Base Case** | Condition that stops recursion | Yes |
| **Recursive Case** | Function calling itself | Yes |

Without a base case, the function runs forever (stack overflow error).

### Factorial Example
```python
def factorial(n):
    if n == 0 or n == 1:  # Base case
        return 1
    else:                  # Recursive case
        return n * factorial(n - 1)

print(factorial(5))  # Output: 120
```

---

## Fibonacci Sequence

**Definition:** Each number is the sum of the two preceding ones: 0, 1, 1, 2, 3, 5, 8, 13...

```python
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

print(fibonacci(7))  # Output: 13
```

---

## Recursion with Lists

### Sum of List
```python
def sum_list(numbers):
    if len(numbers) == 0:
        return 0
    else:
        return numbers[0] + sum_list(numbers[1:])

print(sum_list([1, 2, 3, 4, 5]))  # Output: 15
```

### Find Maximum
```python
def find_max(numbers):
    if len(numbers) == 1:
        return numbers[0]
    else:
        max_of_rest = find_max(numbers[1:])
        return numbers[0] if numbers[0] > max_of_rest else max_of_rest

print(find_max([3, 7, 2, 9, 1]))  # Output: 9
```

---

## Recursion Depth Limit

Python has a recursion limit (default ~1000 calls).

```python
import sys
print(sys.getrecursionlimit())  # Check limit
sys.setrecursionlimit(2000)     # Increase limit (use with caution)
```

---

# Python Generators

## What are Generators?

**Definition:** Generators are functions that can pause and resume execution. They use `yield` instead of `return`.

### Basic Generator
```python
def my_generator():
    yield 1
    yield 2
    yield 3

for value in my_generator():
    print(value)
# Output: 1, 2, 3
```

---

## The yield Keyword

**Definition:** `yield` pauses the function and returns a value. Next call continues from where it left off.

```python
def count_up_to(n):
    count = 1
    while count <= n:
        yield count
        count += 1

for num in count_up_to(5):
    print(num)
# Output: 1, 2, 3, 4, 5
```

| Keyword | Action | Can be called |
|---------|--------|---------------|
| `return` | Terminates function | Once |
| `yield` | Pauses function | Multiple times |

---

## Generators Save Memory

Generators generate values on-the-fly instead of storing everything in memory.

```python
def large_sequence(n):
    for i in range(n):
        yield i

gen = large_sequence(1000000)  # Doesn't create million numbers in memory
print(next(gen))  # Output: 0
print(next(gen))  # Output: 1
```

---

## Using next() with Generators

```python
def simple_gen():
    yield "Emil"
    yield "Tobias"
    yield "Linus"

gen = simple_gen()
print(next(gen))  # Output: Emil
print(next(gen))  # Output: Tobias
print(next(gen))  # Output: Linus
# next(gen)  # Raises StopIteration
```

---

## Generator Expressions

Use parentheses instead of square brackets for generator expressions.

```python
# List comprehension - creates list
list_comp = [x * x for x in range(5)]
print(list_comp)  # [0, 1, 4, 9, 16]

# Generator expression - creates generator
gen_exp = (x * x for x in range(5))
print(list(gen_exp))  # [0, 1, 4, 9, 16]
```

### With sum()
```python
total = sum(x * x for x in range(10))
print(total)  # Output: 285
```

---

## Fibonacci Generator

```python
def fibonacci():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

gen = fibonacci()
for _ in range(10):
    print(next(gen))
# Output: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34
```

---

## Generator Methods

### send() Method
```python
def echo_generator():
    while True:
        received = yield
        print("Received:", received)

gen = echo_generator()
next(gen)  # Prime the generator
gen.send("Hello")  # Output: Received: Hello
```

### close() Method
```python
def my_gen():
    try:
        yield 1
        yield 2
    finally:
        print("Generator closed")

gen = my_gen()
print(next(gen))  # Output: 1
gen.close()       # Output: Generator closed
```

---

## Quick Reference

### Recursion
```python
def recursive_func(n):
    if base_case:      # Stop condition
        return value
    else:
        return recursive_func(n-1)  # Call itself
```

### Generators
```python
def generator_func():
    yield value1
    yield value2

gen = generator_func()
next(gen)  # Get next value
```

---

## Key Takeaways

### ✅ Recursion
- Function calls itself
- Must have base case
- Useful for tree/graph traversal
- Has depth limit (~1000)

### ✅ Generators
- Use `yield` instead of `return`
- Memory efficient
- Lazy evaluation
- Use `next()` to get values
- Generator expressions with `()`

### 🎯 Interview Important
- Recursion base case importance
- Recursion vs iteration
- Generator vs list memory usage
- When to use generators
- `yield` vs `return`

---

**Use recursion for problems with recursive structure, and generators for memory-efficient iteration!**
