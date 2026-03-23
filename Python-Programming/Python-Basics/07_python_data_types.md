# Python Data Types

## What are Data Types?

In programming, **data type** is an important concept. Variables can store **different types of data**, and different types can do **different things**.

---

## Built-in Data Types

Python has the following data types built-in by default:

| Category | Data Types | Description |
|----------|------------|-------------|
| **Text** | `str` | Text/string data |
| **Numeric** | `int`, `float`, `complex` | Numbers |
| **Sequence** | `list`, `tuple`, `range` | Ordered collections |
| **Mapping** | `dict` | Key-value pairs |
| **Set** | `set`, `frozenset` | Unique items |
| **Boolean** | `bool` | True/False |
| **Binary** | `bytes`, `bytearray`, `memoryview` | Binary data |
| **None** | `NoneType` | No value |

---

## Getting the Data Type

Use the `type()` function to get the data type of any variable:

```python
x = 5
print(type(x))  # Output: <class 'int'>

y = "Hello"
print(type(y))  # Output: <class 'str'>

z = 3.14
print(type(z))  # Output: <class 'float'>
```

---

## Data Types by Assignment

In Python, the **data type is set automatically** when you assign a value:

### Text Type
```python
x = "Hello World"
print(type(x))  # <class 'str'>
```

### Numeric Types
```python
x = 20
print(type(x))  # <class 'int'>

x = 20.5
print(type(x))  # <class 'float'>

x = 1j
print(type(x))  # <class 'complex'>
```

### Sequence Types
```python
x = ["apple", "banana", "cherry"]
print(type(x))  # <class 'list'>

x = ("apple", "banana", "cherry")
print(type(x))  # <class 'tuple'>

x = range(6)
print(type(x))  # <class 'range'>
```

### Mapping Type
```python
x = {"name": "John", "age": 36}
print(type(x))  # <class 'dict'>
```

### Set Types
```python
x = {"apple", "banana", "cherry"}
print(type(x))  # <class 'set'>

x = frozenset({"apple", "banana", "cherry"})
print(type(x))  # <class 'frozenset'>
```

### Boolean Type
```python
x = True
print(type(x))  # <class 'bool'>
```

### Binary Types
```python
x = b"Hello"
print(type(x))  # <class 'bytes'>

x = bytearray(5)
print(type(x))  # <class 'bytearray'>

x = memoryview(bytes(5))
print(type(x))  # <class 'memoryview'>
```

### None Type
```python
x = None
print(type(x))  # <class 'NoneType'>
```

---

## Setting Specific Data Types

You can **specify the data type** using constructor functions:

### Text Type
```python
x = str("Hello World")
print(x)         # Output: Hello World
print(type(x))   # <class 'str'>
```

### Numeric Types
```python
x = int(20)
print(x)         # Output: 20
print(type(x))   # <class 'int'>

x = float(20.5)
print(x)         # Output: 20.5
print(type(x))   # <class 'float'>

x = complex(1j)
print(x)         # Output: 1j
print(type(x))   # <class 'complex'>
```

### Sequence Types
```python
x = list(("apple", "banana", "cherry"))
print(x)         # Output: ['apple', 'banana', 'cherry']
print(type(x))   # <class 'list'>

x = tuple(("apple", "banana", "cherry"))
print(x)         # Output: ('apple', 'banana', 'cherry')
print(type(x))   # <class 'tuple'>

x = range(6)
print(list(x))   # Output: [0, 1, 2, 3, 4, 5]
print(type(x))   # <class 'range'>
```

### Mapping Type
```python
x = dict(name="John", age=36)
print(x)         # Output: {'name': 'John', 'age': 36}
print(type(x))   # <class 'dict'>
```

### Set Types
```python
x = set(("apple", "banana", "cherry"))
print(x)         # Output: {'apple', 'banana', 'cherry'}
print(type(x))   # <class 'set'>

x = frozenset(("apple", "banana", "cherry"))
print(x)         # Output: frozenset({'apple', 'banana', 'cherry'})
print(type(x))   # <class 'frozenset'>
```

### Boolean Type
```python
x = bool(5)
print(x)         # Output: True
print(type(x))   # <class 'bool'>
```

### Binary Types
```python
x = bytes(5)
print(x)         # Output: b'\x00\x00\x00\x00\x00'
print(type(x))   # <class 'bytes'>

x = bytearray(5)
print(x)         # Output: bytearray(b'\x00\x00\x00\x00\x00')
print(type(x))   # <class 'bytearray'>

x = memoryview(bytes(5))
print(x)         # Output: <memory at 0x...>
print(type(x))   # <class 'memoryview'>
```

---

## Common Data Types Explained

### 1. String (str)
Text data enclosed in quotes:
```python
name = "Alice"
message = 'Hello World'
```

### 2. Integer (int)
Whole numbers without decimals:
```python
age = 25
count = -10
```

### 3. Float (float)
Numbers with decimals:
```python
price = 19.99
temperature = -5.5
```

### 4. Boolean (bool)
True or False values:
```python
is_active = True
is_complete = False
```

### 5. List (list)
Ordered, changeable collection:
```python
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
```

### 6. Tuple (tuple)
Ordered, unchangeable collection:
```python
coordinates = (10, 20)
colors = ("red", "green", "blue")
```

### 7. Dictionary (dict)
Key-value pairs:
```python
person = {"name": "John", "age": 30, "city": "New York"}
```

### 8. Set (set)
Unordered collection of unique items:
```python
unique_numbers = {1, 2, 3, 4, 5}
```

### 9. None (NoneType)
Represents no value or null:
```python
result = None
```

---

## Quick Reference Table

| Data Type | Example | Mutable? | Ordered? |
|-----------|---------|----------|----------|
| `str` | `"Hello"` | No | Yes |
| `int` | `42` | N/A | N/A |
| `float` | `3.14` | N/A | N/A |
| `bool` | `True` | N/A | N/A |
| `list` | `[1, 2, 3]` | Yes | Yes |
| `tuple` | `(1, 2, 3)` | No | Yes |
| `dict` | `{"key": "value"}` | Yes | Yes (3.7+) |
| `set` | `{1, 2, 3}` | Yes | No |
| `None` | `None` | N/A | N/A |

---

## Type Conversion Examples

### String to Number
```python
x = "100"
y = int(x)
print(y)         # Output: 100
print(type(y))   # <class 'int'>
```

### Number to String
```python
x = 100
y = str(x)
print(y)         # Output: "100"
print(type(y))   # <class 'str'>
```

### List to Tuple
```python
x = [1, 2, 3]
y = tuple(x)
print(y)         # Output: (1, 2, 3)
print(type(y))   # <class 'tuple'>
```

### String to List
```python
x = "Hello"
y = list(x)
print(y)         # Output: ['H', 'e', 'l', 'l', 'o']
```

---

## Practical Examples

### Example 1: Student Information
```python
# Different data types in use
student_name = "Alice"           # str
student_age = 20                 # int
student_gpa = 3.85              # float
is_enrolled = True              # bool
courses = ["Math", "Science"]   # list
grades = {"Math": 95, "Science": 88}  # dict

print("Name:", student_name, type(student_name))
print("Age:", student_age, type(student_age))
print("GPA:", student_gpa, type(student_gpa))
print("Enrolled:", is_enrolled, type(is_enrolled))
```

### Example 2: Type Checking
```python
def check_type(value):
    print(f"Value: {value}")
    print(f"Type: {type(value)}")
    print("-" * 20)

check_type(42)
check_type(3.14)
check_type("Hello")
check_type([1, 2, 3])
check_type(True)
```

---

## Key Takeaways

### ✅ Remember
- Python has **many built-in data types**
- Use `type()` to **check data type**
- Data type is **set automatically** when you assign a value
- You can **specify data type** using constructor functions
- Different data types have **different capabilities**

### 🎯 Most Common Types
1. **str** - for text
2. **int** - for whole numbers
3. **float** - for decimal numbers
4. **bool** - for True/False
5. **list** - for collections
6. **dict** - for key-value data

---

**Understanding data types is crucial for writing effective Python programs!**