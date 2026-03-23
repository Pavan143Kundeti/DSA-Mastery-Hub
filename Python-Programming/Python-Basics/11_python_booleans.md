# Python Booleans

## What are Booleans?

**Boolean** is a data type that represents one of two values: **True** or **False**.

**Definition (Interview):** Booleans are logical data types used for conditional logic and decision-making in programs. Named after mathematician George Boole.

---

## Boolean Values

In programming, you often need to know if an expression is **True** or **False**.

### Comparison Operations
```python
print(10 > 9)   # True
print(10 == 9)  # False
print(10 < 9)   # False
```

### If Statements
```python
a = 200
b = 33

if b > a:
    print("b is greater than a")
else:
    print("b is not greater than a")
# Output: b is not greater than a
```

---

## The bool() Function

The `bool()` function evaluates any value and returns **True** or **False**.

```python
print(bool("Hello"))  # True
print(bool(15))       # True

x = "Hello"
y = 15
print(bool(x))        # True
print(bool(y))        # True
```

---

## Truthy and Falsy Values

**Interview Concept:** In Python, values are classified as "truthy" or "falsy" based on their boolean evaluation.

### Most Values are True (Truthy)

Almost any value with **content** evaluates to **True**:

```python
bool("abc")                        # True - non-empty string
bool(123)                          # True - non-zero number
bool(["apple", "cherry"])          # True - non-empty list
bool({"name": "John"})             # True - non-empty dict
bool((1, 2))                       # True - non-empty tuple
```

### Values that are False (Falsy)

**Interview Important:** Memorize these falsy values:

| Value | Type | Example |
|-------|------|---------|
| `False` | Boolean | `bool(False)` → False |
| `None` | NoneType | `bool(None)` → False |
| `0` | Integer | `bool(0)` → False |
| `0.0` | Float | `bool(0.0)` → False |
| `""` | Empty string | `bool("")` → False |
| `[]` | Empty list | `bool([])` → False |
| `()` | Empty tuple | `bool(())` → False |
| `{}` | Empty dict | `bool({})` → False |

```python
# All return False
print(bool(False))
print(bool(None))
print(bool(0))
print(bool(""))
print(bool([]))
print(bool(()))
print(bool({}))
```

### Custom Class with __len__
```python
class myclass():
    def __len__(self):
        return 0

myobj = myclass()
print(bool(myobj))  # False (because __len__ returns 0)
```

---

## Functions Returning Booleans

### Basic Boolean Function
```python
def myFunction():
    return True

print(myFunction())  # True
```

### Using Boolean in Conditions
```python
def myFunction():
    return True

if myFunction():
    print("YES!")
else:
    print("NO!")
# Output: YES!
```

---

## Built-in Boolean Functions

### isinstance() Function
**Interview Important:** Check if object is of a certain type.

```python
x = 200
print(isinstance(x, int))     # True
print(isinstance(x, str))     # False

name = "Alice"
print(isinstance(name, str))  # True
```

### Other Boolean Functions
```python
# Check string content
print("hello".isalpha())      # True
print("123".isdigit())        # True
print("hello123".isalnum())   # True

# Check list/string
numbers = [1, 2, 3]
print(3 in numbers)           # True
print(5 not in numbers)       # True
```

---

## Boolean Operators

**Interview Concept:** Logical operators combine boolean expressions.

### AND, OR, NOT
```python
# AND - both must be True
print(True and True)    # True
print(True and False)   # False

# OR - at least one must be True
print(True or False)    # True
print(False or False)   # False

# NOT - reverses the value
print(not True)         # False
print(not False)        # True
```

### Practical Examples
```python
age = 25
has_license = True

# Can drive if age >= 18 AND has license
can_drive = age >= 18 and has_license
print(can_drive)  # True

# Weekend if Saturday OR Sunday
day = "Saturday"
is_weekend = day == "Saturday" or day == "Sunday"
print(is_weekend)  # True
```

---

## Common Interview Questions

### Q1: What values are falsy in Python?
**Answer:** `False`, `None`, `0`, `0.0`, `""`, `[]`, `()`, `{}`

### Q2: Difference between `==` and `is`?
```python
a = [1, 2, 3]
b = [1, 2, 3]
c = a

print(a == b)  # True (same values)
print(a is b)  # False (different objects)
print(a is c)  # True (same object)
```

### Q3: What is short-circuit evaluation?
```python
# AND stops at first False
result = False and print("This won't print")

# OR stops at first True
result = True or print("This won't print")
```

---

## Key Takeaways

### ✅ Remember
- Booleans have only **two values**: True or False
- Used for **conditional logic** and **decision making**
- **Truthy**: Non-empty, non-zero values
- **Falsy**: Empty values, 0, None, False
- `bool()` function converts any value to boolean

### 🎯 Interview Points
- **8 falsy values** in Python (memorize them)
- `isinstance()` checks object type
- **Logical operators**: and, or, not
- **Comparison operators**: ==, !=, <, >, <=, >=
- **Short-circuit evaluation** in boolean operations

---

**Booleans are fundamental for control flow and logic in Python programs!**