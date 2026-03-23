# Python Range

## What is range()?

**Definition:** The `range()` function returns an immutable sequence of numbers, commonly used for looping.

**Data Type:** `range` (its own data type)

**Immutable:** Cannot be modified after creation.

---

## Creating Ranges

### Syntax
```python
range(stop)              # One argument
range(start, stop)       # Two arguments
range(start, stop, step) # Three arguments
```

---

## One Argument - range(stop)

**Default:** Start = 0, Step = 1

```python
x = range(10)
print(list(x))
# Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**Note:** Stop value is exclusive (not included).

---

## Two Arguments - range(start, stop)

```python
x = range(3, 10)
print(list(x))
# Output: [3, 4, 5, 6, 7, 8, 9]
```

---

## Three Arguments - range(start, stop, step)

**Step:** Difference between each number.

```python
x = range(3, 10, 2)
print(list(x))
# Output: [3, 5, 7, 9]
```

---

## Range Parameters Table

| Parameter | Default | Description | Example |
|-----------|---------|-------------|---------|
| `start` | 0 | Starting number (inclusive) | `range(2, 10)` |
| `stop` | Required | Ending number (exclusive) | `range(10)` |
| `step` | 1 | Increment value | `range(0, 10, 2)` |

---

## Using Ranges in For Loops

```python
for i in range(10):
    print(i)
# Output: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
```

---

## Display Ranges with list()

Range objects are not directly displayable. Convert to list for display.

```python
print(list(range(5)))
# Output: [0, 1, 2, 3, 4]

print(list(range(1, 6)))
# Output: [1, 2, 3, 4, 5]

print(list(range(5, 20, 3)))
# Output: [5, 8, 11, 14, 17]
```

---

## Slicing Ranges

```python
r = range(10)

print(r[2])      # Output: 2 (value at index 2)
print(r[:3])     # Output: range(0, 3)
print(list(r[:3]))  # Output: [0, 1, 2]
```

---

## Membership Testing

Use `in` operator to check if a number exists in range.

```python
r = range(0, 10, 2)

print(6 in r)    # Output: True
print(7 in r)    # Output: False
```

| Result | Meaning |
|--------|---------|
| `True` | Number is in range |
| `False` | Number is not in range |

---

## Length of Range

```python
r = range(0, 10, 2)
print(len(r))
# Output: 5
```

---

## Common Range Patterns

### Count 0 to 9
```python
range(10)  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### Count 1 to 10
```python
range(1, 11)  # [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### Even Numbers
```python
range(0, 11, 2)  # [0, 2, 4, 6, 8, 10]
```

### Odd Numbers
```python
range(1, 11, 2)  # [1, 3, 5, 7, 9]
```

### Countdown
```python
range(10, 0, -1)  # [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
```

---

## Quick Reference

| Example | Output |
|---------|--------|
| `range(5)` | `[0, 1, 2, 3, 4]` |
| `range(2, 5)` | `[2, 3, 4]` |
| `range(0, 10, 2)` | `[0, 2, 4, 6, 8]` |
| `range(10, 0, -1)` | `[10, 9, 8, 7, 6, 5, 4, 3, 2, 1]` |

---

## Key Takeaways

### ✅ Remember
- **range()** creates immutable sequence of numbers
- **Stop value** is exclusive (not included)
- **Default start** is 0
- **Default step** is 1
- **Use list()** to display range
- **Supports** slicing, membership testing, len()
- **Commonly used** in for loops

### 🎯 Interview Important
- range() returns range object, not list
- Stop value is exclusive
- Negative step for countdown
- Memory efficient (doesn't store all numbers)
- range() vs list differences

---

**Use range() for efficient number sequences in loops and iterations!**
