# Python Operators

## What are Operators?

**Definition:** Operators are special symbols used to perform operations on variables and values.

```python
print(10 + 5)  # + is an operator
```

---

## Types of Operators

Python has 7 types of operators:
1. Arithmetic Operators
2. Assignment Operators
3. Comparison Operators
4. Logical Operators
5. Identity Operators
6. Membership Operators
7. Bitwise Operators

---

## 1. Arithmetic Operators

**Definition:** Used to perform mathematical operations on numeric values.

| Operator | Name | Description | Example | Result |
|----------|------|-------------|---------|--------|
| `+` | Addition | Adds two values | `10 + 5` | `15` |
| `-` | Subtraction | Subtracts right from left | `10 - 5` | `5` |
| `*` | Multiplication | Multiplies two values | `10 * 5` | `50` |
| `/` | Division | Divides left by right (float) | `10 / 5` | `2.0` |
| `%` | Modulus | Returns remainder | `10 % 3` | `1` |
| `**` | Exponentiation | Raises to power | `2 ** 3` | `8` |
| `//` | Floor Division | Divides and rounds down | `10 // 3` | `3` |

### Examples
```python
x = 15
y = 4

print(x + y)   # 19
print(x - y)   # 11
print(x * y)   # 60
print(x / y)   # 3.75
print(x % y)   # 3
print(x ** y)  # 50625
print(x // y)  # 3
```

### Division Types
```python
# / returns float
print(12 / 5)   # 2.4

# // returns integer (rounds down)
print(12 // 5)  # 2
```

---

## 2. Assignment Operators

**Definition:** Used to assign values to variables.

| Operator | Example | Same As | Description |
|----------|---------|---------|-------------|
| `=` | `x = 5` | `x = 5` | Assign value |
| `+=` | `x += 3` | `x = x + 3` | Add and assign |
| `-=` | `x -= 3` | `x = x - 3` | Subtract and assign |
| `*=` | `x *= 3` | `x = x * 3` | Multiply and assign |
| `/=` | `x /= 3` | `x = x / 3` | Divide and assign |
| `%=` | `x %= 3` | `x = x % 3` | Modulus and assign |
| `//=` | `x //= 3` | `x = x // 3` | Floor divide and assign |
| `**=` | `x **= 3` | `x = x ** 3` | Exponent and assign |

### Examples
```python
x = 10
x += 5   # x = 15
x -= 3   # x = 12
x *= 2   # x = 24
x /= 4   # x = 6.0
```

### Walrus Operator (:=)
**Definition:** Assigns value within an expression (Python 3.8+).

```python
# Assign and use in one line
numbers = [1, 2, 3, 4, 5]
if (count := len(numbers)) > 3:
    print(f"List has {count} elements")
# Output: List has 5 elements
```

---

## 3. Comparison Operators

**Definition:** Used to compare two values, returns True or False.

| Operator | Name | Description | Example | Result |
|----------|------|-------------|---------|--------|
| `==` | Equal | Checks if equal | `5 == 5` | `True` |
| `!=` | Not Equal | Checks if not equal | `5 != 3` | `True` |
| `>` | Greater Than | Left > Right | `5 > 3` | `True` |
| `<` | Less Than | Left < Right | `5 < 3` | `False` |
| `>=` | Greater or Equal | Left >= Right | `5 >= 5` | `True` |
| `<=` | Less or Equal | Left <= Right | `5 <= 3` | `False` |

### Examples
```python
x = 5
y = 3

print(x == y)  # False
print(x != y)  # True
print(x > y)   # True
print(x < y)   # False
print(x >= y)  # True
print(x <= y)  # False
```

### Chaining Comparisons
```python
x = 5
print(1 < x < 10)  # True (same as: 1 < x and x < 10)
```

---

## 4. Logical Operators

**Definition:** Used to combine conditional statements.

| Operator | Description | Example | Result |
|----------|-------------|---------|--------|
| `and` | True if both are True | `True and False` | `False` |
| `or` | True if at least one is True | `True or False` | `True` |
| `not` | Reverses the result | `not True` | `False` |

### Truth Tables

**AND Operator:**
| A | B | A and B |
|---|---|---------|
| True | True | True |
| True | False | False |
| False | True | False |
| False | False | False |

**OR Operator:**
| A | B | A or B |
|---|---|--------|
| True | True | True |
| True | False | True |
| False | True | True |
| False | False | False |

### Examples
```python
x = 5

print(x > 0 and x < 10)      # True
print(x < 5 or x > 10)       # False
print(not(x > 3 and x < 10)) # False
```

---

## 5. Identity Operators

**Definition:** Used to compare objects' memory locations, not their values.

| Operator | Description | Example |
|----------|-------------|---------|
| `is` | True if same object | `x is y` |
| `is not` | True if different objects | `x is not y` |

### Examples
```python
x = ["apple", "banana"]
y = ["apple", "banana"]
z = x

print(x is z)    # True (same object)
print(x is y)    # False (different objects)
print(x == y)    # True (same values)
print(x is not y) # True
```

### Difference: is vs ==
- `is` checks if **same object in memory**
- `==` checks if **values are equal**

```python
x = [1, 2, 3]
y = [1, 2, 3]

print(x == y)  # True (same values)
print(x is y)  # False (different objects)
```

---

## 6. Membership Operators

**Definition:** Used to test if a value exists in a sequence.

| Operator | Description | Example |
|----------|-------------|---------|
| `in` | True if value exists in sequence | `x in y` |
| `not in` | True if value doesn't exist | `x not in y` |

### Examples
```python
fruits = ["apple", "banana", "cherry"]

print("banana" in fruits)      # True
print("pineapple" not in fruits) # True

# Works with strings
text = "Hello World"
print("H" in text)       # True
print("hello" in text)   # False (case-sensitive)
print("z" not in text)   # True
```

---

## 7. Bitwise Operators

**Definition:** Used to perform operations on binary numbers.

| Operator | Name | Description | Example |
|----------|------|-------------|---------|
| `&` | AND | Sets bit to 1 if both are 1 | `6 & 3` → `2` |
| `\|` | OR | Sets bit to 1 if one is 1 | `6 \| 3` → `7` |
| `^` | XOR | Sets bit to 1 if only one is 1 | `6 ^ 3` → `5` |
| `~` | NOT | Inverts all bits | `~6` → `-7` |
| `<<` | Left Shift | Shifts bits left | `6 << 1` → `12` |
| `>>` | Right Shift | Shifts bits right | `6 >> 1` → `3` |

### Examples
```python
# Binary: 6 = 0110, 3 = 0011

print(6 & 3)   # 2 (0010)
print(6 | 3)   # 7 (0111)
print(6 ^ 3)   # 5 (0101)
```

---

## Operator Precedence

**Definition:** The order in which operations are performed in an expression.

### Precedence Table (Highest to Lowest)

| Priority | Operator | Description |
|----------|----------|-------------|
| 1 | `()` | Parentheses |
| 2 | `**` | Exponentiation |
| 3 | `+x`, `-x`, `~x` | Unary plus, minus, NOT |
| 4 | `*`, `/`, `//`, `%` | Multiplication, Division |
| 5 | `+`, `-` | Addition, Subtraction |
| 6 | `<<`, `>>` | Bitwise shifts |
| 7 | `&` | Bitwise AND |
| 8 | `^` | Bitwise XOR |
| 9 | `\|` | Bitwise OR |
| 10 | `==`, `!=`, `>`, `<`, `>=`, `<=`, `is`, `in` | Comparisons |
| 11 | `not` | Logical NOT |
| 12 | `and` | Logical AND |
| 13 | `or` | Logical OR |

### Examples
```python
# Parentheses first
print((6 + 3) - (6 + 3))  # 0

# Multiplication before addition
print(100 + 5 * 3)  # 115 (not 315)

# Left to right for same precedence
print(5 + 4 - 7 + 3)  # 5

# Complex expression
print(2 + 3 * 4)  # 14 (not 20)
```

---

## Quick Reference Summary

### Most Common Operators
```python
# Arithmetic
x + y, x - y, x * y, x / y, x % y, x ** y, x // y

# Comparison
x == y, x != y, x > y, x < y, x >= y, x <= y

# Logical
x and y, x or y, not x

# Assignment
x = 5, x += 5, x -= 5, x *= 5

# Membership
x in y, x not in y

# Identity
x is y, x is not y
```

---

## Key Takeaways

### ✅ Remember
- **Arithmetic**: Math operations (+, -, *, /, %, **, //)
- **Comparison**: Returns True/False (==, !=, >, <, >=, <=)
- **Logical**: Combine conditions (and, or, not)
- **Assignment**: Assign values (=, +=, -=, *=)
- **Identity**: Check same object (is, is not)
- **Membership**: Check existence (in, not in)
- **Precedence**: () has highest, or has lowest

### 🎯 Interview Important
- Difference between `==` and `is`
- Difference between `/` and `//`
- Operator precedence order
- Walrus operator `:=` (Python 3.8+)
- Logical operator short-circuit evaluation

---

**Master operators to write efficient and readable Python code!**