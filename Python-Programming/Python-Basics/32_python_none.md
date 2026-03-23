# Python None

## What is None?

**Definition:** None is a special constant in Python that represents the absence of a value.

**Data Type:** NoneType
**Instance:** None is the only instance of NoneType object

---

## Basic None Usage

### Assign None
```python
x = None
print(x)  # Output: None
```

### Check Data Type
```python
x = None
print(type(x))  # Output: <class 'NoneType'>
```

---

## Comparing to None

**Important:** Use `is` or `is not` operators, NOT `==` or `!=`.

### Using is
```python
result = None

if result is None:
    print("No result yet")
else:
    print("Result is ready")

# Output: No result yet
```

### Using is not
```python
result = None

if result is not None:
    print("Result is ready")
else:
    print("No result yet")

# Output: No result yet
```

---

## Why Use 'is' Instead of '=='?

| Operator | Purpose | Example |
|----------|---------|---------|
| `is` | Identity comparison (same object) | `x is None` |
| `==` | Value comparison (equal values) | `x == None` |

**Best Practice:** Always use `is` with None.

```python
# Correct
if value is None:
    pass

# Avoid (works but not recommended)
if value == None:
    pass
```

---

## None as Boolean

None evaluates to `False` in boolean context.

```python
print(bool(None))  # Output: False

# In conditions
x = None
if x:
    print("This won't print")
else:
    print("x is falsy")  # This prints
```

---

## Functions Returning None

Functions without explicit `return` statement return None by default.

### Function Without Return
```python
def myfunc():
    x = 5  # No return statement

result = myfunc()
print(result)  # Output: None
```

### Function With Empty Return
```python
def myfunc():
    return  # Empty return

result = myfunc()
print(result)  # Output: None
```

### Function With Conditional Return
```python
def get_value(condition):
    if condition:
        return "Success"
    # No return for False case

result = get_value(False)
print(result)  # Output: None
```

---

## Common Use Cases

### 1. Default Parameter Values
```python
def greet(name=None):
    if name is None:
        name = "Guest"
    print(f"Hello, {name}!")

greet()        # Output: Hello, Guest!
greet("Alice") # Output: Hello, Alice!
```

### 2. Optional Variables
```python
user_input = None
config = None

# Later in code
if user_input is not None:
    process_input(user_input)
```

### 3. Initialization
```python
# Initialize variables
result = None
data = None
connection = None

# Use later when values are available
```

### 4. Error Handling
```python
def safe_divide(a, b):
    if b == 0:
        return None  # Indicate error
    return a / b

result = safe_divide(10, 0)
if result is None:
    print("Division by zero!")
else:
    print(f"Result: {result}")
```

---

## None vs Other "Empty" Values

| Value | Type | Boolean | Use Case |
|-------|------|---------|----------|
| `None` | NoneType | False | No value/not set |
| `""` | str | False | Empty string |
| `[]` | list | False | Empty list |
| `{}` | dict | False | Empty dictionary |
| `0` | int | False | Zero number |
| `False` | bool | False | Boolean false |

### Comparison Example
```python
values = [None, "", [], {}, 0, False]

for value in values:
    print(f"{repr(value):>8} is {bool(value)}")

# Output:
#     None is False
#       '' is False
#       [] is False
#       {} is False
#        0 is False
#    False is False
```

---

## Practical Examples

### Database Query Result
```python
def find_user(user_id):
    # Simulate database query
    if user_id == 1:
        return {"name": "Alice", "age": 25}
    else:
        return None  # User not found

user = find_user(999)
if user is None:
    print("User not found")
else:
    print(f"Found user: {user['name']}")
```

### Configuration Settings
```python
class Config:
    def __init__(self):
        self.database_url = None
        self.api_key = None
        self.debug_mode = None
    
    def is_configured(self):
        return all([
            self.database_url is not None,
            self.api_key is not None,
            self.debug_mode is not None
        ])

config = Config()
print(config.is_configured())  # False
```

### Optional Processing
```python
def process_data(data, processor=None):
    if processor is None:
        # Default processing
        return data.upper()
    else:
        # Custom processing
        return processor(data)

result1 = process_data("hello")           # HELLO
result2 = process_data("hello", str.lower) # hello
```

---

## None in Data Structures

### Lists with None
```python
items = [1, None, 3, None, 5]

# Filter out None values
filtered = [x for x in items if x is not None]
print(filtered)  # [1, 3, 5]
```

### Dictionary with None Values
```python
data = {
    "name": "Alice",
    "age": None,
    "email": "alice@example.com"
}

# Check for None values
for key, value in data.items():
    if value is None:
        print(f"{key} is not set")
```

### Function Arguments
```python
def create_user(name, email=None, phone=None):
    user = {"name": name}
    
    if email is not None:
        user["email"] = email
    
    if phone is not None:
        user["phone"] = phone
    
    return user

user1 = create_user("Alice")
user2 = create_user("Bob", "bob@example.com")
```

---

## Common Mistakes

### Wrong Comparison
```python
# Wrong - don't use ==
if value == None:
    pass

# Correct - use is
if value is None:
    pass
```

### Forgetting Return Statement
```python
def get_data():
    data = fetch_from_api()
    # Forgot to return data!

result = get_data()
print(result)  # None (unexpected!)
```

### None vs Empty String
```python
name = ""  # Empty string, not None

# Wrong assumption
if name is None:
    print("Name not provided")  # Won't execute

# Better check
if not name:  # Checks for empty string too
    print("Name not provided")
```

---

## Quick Reference

### Basic Operations
```python
# Assignment
x = None

# Type check
type(x)  # <class 'NoneType'>

# Comparison
x is None      # True
x is not None  # False

# Boolean
bool(None)     # False
```

### Common Patterns
```python
# Default parameter
def func(param=None):
    if param is None:
        param = default_value

# Error indication
def risky_operation():
    try:
        return success_value
    except:
        return None

# Optional processing
if value is not None:
    process(value)
```

---

## Key Takeaways

### ✅ Remember
- **None** represents absence of value
- **NoneType** is None's data type
- **Use `is`** for None comparisons, not `==`
- **Functions** return None by default
- **None** evaluates to False in boolean context
- **Common use:** default parameters, error indication
- **None ≠ empty string/list/dict** (different concepts)

### 🎯 Interview Important
- What None represents in Python
- Why use `is` instead of `==` with None
- When functions return None automatically
- Difference between None and other falsy values
- Common use cases for None
- None's role in optional parameters
- Boolean evaluation of None

---

**Use None to represent "no value" or "not set" states in your Python programs!**