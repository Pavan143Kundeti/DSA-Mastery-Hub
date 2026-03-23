# Python Casting

## What is Casting?

**Casting** is when you want to **specify a type** for a variable. This is done using **constructor functions**.

Python uses **classes** to define data types, so casting uses these class constructors.

---

## Casting Functions

Python has three main casting functions:

| Function | Purpose | Example |
|----------|---------|---------|
| `int()` | Convert to integer | `int(3.5)` → `3` |
| `float()` | Convert to float | `float(5)` → `5.0` |
| `str()` | Convert to string | `str(10)` → `"10"` |

---

## Integer Casting - int()

The `int()` function constructs an **integer** from:
- Integer literal
- Float literal (removes all decimals)
- String literal (if string represents a whole number)

### Integer Examples
```python
x = int(1)      # x will be 1
y = int(2.8)    # y will be 2 (decimal removed)
z = int("3")    # z will be 3 (string to int)

print(x)        # Output: 1
print(y)        # Output: 2
print(z)        # Output: 3

print(type(x))  # <class 'int'>
print(type(y))  # <class 'int'>
print(type(z))  # <class 'int'>
```

### More int() Examples
```python
# From float - removes decimals
print(int(5.9))     # Output: 5
print(int(-3.7))    # Output: -3
print(int(10.0))    # Output: 10

# From string - must be valid number
print(int("100"))   # Output: 100
print(int("-50"))   # Output: -50

# This will cause an error:
# print(int("3.5"))   # Error! String has decimal
# print(int("hello")) # Error! Not a number
```

---

## Float Casting - float()

The `float()` function constructs a **float** from:
- Integer literal
- Float literal
- String literal (if string represents a number)

### Float Examples
```python
x = float(1)       # x will be 1.0
y = float(2.8)     # y will be 2.8
z = float("3")     # z will be 3.0
w = float("4.2")   # w will be 4.2

print(x)           # Output: 1.0
print(y)           # Output: 2.8
print(z)           # Output: 3.0
print(w)           # Output: 4.2

print(type(x))     # <class 'float'>
print(type(y))     # <class 'float'>
print(type(z))     # <class 'float'>
print(type(w))     # <class 'float'>
```

### More float() Examples
```python
# From integer
print(float(10))      # Output: 10.0
print(float(-5))      # Output: -5.0

# From string
print(float("3.14"))  # Output: 3.14
print(float("-2.5"))  # Output: -2.5
print(float("100"))   # Output: 100.0

# This will cause an error:
# print(float("hello"))  # Error! Not a number
```

---

## String Casting - str()

The `str()` function constructs a **string** from:
- String literals
- Integer literals
- Float literals
- Many other data types

### String Examples
```python
x = str("s1")    # x will be 's1'
y = str(2)       # y will be '2'
z = str(3.0)     # z will be '3.0'

print(x)         # Output: s1
print(y)         # Output: 2
print(z)         # Output: 3.0

print(type(x))   # <class 'str'>
print(type(y))   # <class 'str'>
print(type(z))   # <class 'str'>
```

### More str() Examples
```python
# From numbers
print(str(100))       # Output: "100"
print(str(3.14))      # Output: "3.14"
print(str(-50))       # Output: "-50"

# From boolean
print(str(True))      # Output: "True"
print(str(False))     # Output: "False"

# From list
print(str([1, 2, 3])) # Output: "[1, 2, 3]"
```

---

## Casting Conversion Table

| From | To | Function | Input | Output | Type |
|------|-----|----------|-------|--------|------|
| float | int | `int(5.9)` | `5.9` | `5` | int |
| string | int | `int("10")` | `"10"` | `10` | int |
| int | float | `float(5)` | `5` | `5.0` | float |
| string | float | `float("3.14")` | `"3.14"` | `3.14` | float |
| int | string | `str(10)` | `10` | `"10"` | str |
| float | string | `str(3.14)` | `3.14` | `"3.14"` | str |

---

## Practical Examples

### Example 1: User Input Conversion
```python
# Input always returns string, need to convert
age_input = input("Enter your age: ")  # Returns string
age = int(age_input)                   # Convert to integer
print("Next year you will be", age + 1)
```

### Example 2: Price Calculator
```python
price_str = "19.99"
quantity_str = "3"

# Convert strings to numbers
price = float(price_str)
quantity = int(quantity_str)

# Calculate total
total = price * quantity
print(f"Total: ${total}")  # Output: Total: $59.97
```

### Example 3: Display Formatting
```python
score = 95
percentage = 0.95

# Convert to strings for display
score_str = str(score)
percentage_str = str(percentage)

print("Score: " + score_str)           # Output: Score: 95
print("Percentage: " + percentage_str) # Output: Percentage: 0.95
```

### Example 4: Mixed Operations
```python
# Cannot add string and number directly
x = "10"
y = 5

# Must convert first
result = int(x) + y
print(result)  # Output: 15

# Or convert to string
result = x + str(y)
print(result)  # Output: 105 (string concatenation)
```

---

## Common Casting Errors

### Error 1: Invalid String to int
```python
# ❌ Wrong - string has decimal
# x = int("3.5")  # ValueError

# ✅ Correct - convert to float first
x = int(float("3.5"))
print(x)  # Output: 3
```

### Error 2: Non-numeric String
```python
# ❌ Wrong - not a number
# x = int("hello")  # ValueError

# ✅ Correct - check before converting
text = "hello"
if text.isdigit():
    x = int(text)
else:
    print("Not a valid number")
```

### Error 3: Adding String and Number
```python
# ❌ Wrong - can't add different types
x = "10"
y = 5
# result = x + y  # TypeError

# ✅ Correct - convert first
result = int(x) + y
print(result)  # Output: 15
```

---

## When to Use Casting

### 1. **User Input**
```python
age = int(input("Enter age: "))
price = float(input("Enter price: "))
```

### 2. **String to Number Calculations**
```python
num_str = "100"
result = int(num_str) * 2
```

### 3. **Number to String for Display**
```python
score = 95
message = "Your score is " + str(score)
```

### 4. **Data Type Consistency**
```python
values = [1, 2.5, "3"]
# Convert all to float
values_float = [float(x) for x in values]
```

---

## Quick Reference

### Casting Rules
- `int()` **removes decimals** (doesn't round)
- `float()` **adds decimal point** if needed
- `str()` **converts anything** to text
- **Always check** if string is valid before casting
- **Cannot cast** complex numbers to int or float

### Common Patterns
```python
# String to number
x = int("10")
y = float("3.14")

# Number to string
x = str(100)
y = str(3.14)

# Float to int (removes decimal)
x = int(5.9)  # Result: 5

# Int to float (adds .0)
x = float(5)  # Result: 5.0
```

---

## Key Takeaways

### ✅ Remember
- **Casting** = converting one type to another
- Use `int()`, `float()`, `str()` functions
- `int()` removes decimals, doesn't round
- User input is always **string** - must convert
- Check validity before casting to avoid errors

### 🎯 Most Common Uses
1. Converting **user input** to numbers
2. Converting **numbers to strings** for display
3. Ensuring **consistent data types** in calculations
4. **Data cleaning** and preparation

---

**Casting is essential for handling different data types in Python programs!**