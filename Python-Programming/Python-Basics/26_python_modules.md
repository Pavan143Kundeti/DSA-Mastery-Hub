# Python Modules

## What is a Module?

**Definition:** A module is a code library - a file containing functions you want to include in your application.

**Think of it as:** A toolbox with useful functions and variables.

---

## Create a Module

Save code in a file with `.py` extension.

### Example: mymodule.py
```python
def greeting(name):
    print("Hello, " + name)

person1 = {
    "name": "John",
    "age": 36,
    "country": "Norway"
}
```

---

## Use a Module

Use `import` statement to use a module.

```python
import mymodule

mymodule.greeting("Jonathan")
# Output: Hello, Jonathan
```

**Syntax:** `module_name.function_name`

---

## Variables in Modules

Modules can contain functions, variables, arrays, dictionaries, objects, etc.

```python
import mymodule

a = mymodule.person1["age"]
print(a)  # Output: 36
```

---

## Module Naming

| Rule | Description |
|------|-------------|
| File extension | Must be `.py` |
| Name | Can be any valid filename |
| Usage | `import filename` (without .py) |

---

## Re-naming a Module (Alias)

Use `as` keyword to create an alias.

```python
import mymodule as mx

a = mx.person1["age"]
print(a)  # Output: 36
```

**Benefits:** Shorter names, avoid conflicts.

---

## Built-in Modules

Python has many built-in modules.

```python
import platform

x = platform.system()
print(x)  # Output: Windows/Linux/Darwin
```

### Common Built-in Modules
- `math` - Mathematical functions
- `datetime` - Date and time
- `random` - Random numbers
- `os` - Operating system interface
- `sys` - System parameters

---

## dir() Function

Lists all function/variable names in a module.

```python
import platform

x = dir(platform)
print(x)  # Lists all names in platform module
```

**Use:** Explore what's available in a module.

---

## Import From Module

Import only specific parts using `from` keyword.

### mymodule.py
```python
def greeting(name):
    print("Hello, " + name)

person1 = {
    "name": "John",
    "age": 36,
    "country": "Norway"
}
```

### Import Specific Items
```python
from mymodule import person1

print(person1["age"])  # Output: 36
```

**Note:** Don't use module name when using `from` import.

### Import Multiple Items
```python
from mymodule import greeting, person1

greeting("Alice")
print(person1["name"])
```

### Import All (Not Recommended)
```python
from mymodule import *

greeting("Bob")  # Can use directly
```

---

## Import Patterns

| Pattern | Syntax | Usage |
|---------|--------|-------|
| Full import | `import module` | `module.function()` |
| Alias import | `import module as alias` | `alias.function()` |
| Specific import | `from module import item` | `item()` |
| Multiple import | `from module import a, b` | `a()`, `b()` |

---

# Python Datetime

## What is Datetime?

**Definition:** Python doesn't have a built-in date data type. Use `datetime` module to work with dates.

---

## Current Date and Time

```python
import datetime

x = datetime.datetime.now()
print(x)
# Output: 2026-03-23 14:25:33.065059
```

**Format:** Year-Month-Day Hour:Minute:Second.Microsecond

---

## Date Components

```python
import datetime

x = datetime.datetime.now()

print(x.year)        # 2026
print(x.month)       # 3
print(x.day)         # 23
print(x.hour)        # 14
print(x.minute)      # 25
print(x.strftime("%A"))  # Sunday
```

---

## Creating Date Objects

Use `datetime()` constructor.

```python
import datetime

x = datetime.datetime(2020, 5, 17)
print(x)  # Output: 2020-05-17 00:00:00
```

### Parameters
| Parameter | Required | Default |
|-----------|----------|---------|
| year | Yes | - |
| month | Yes | - |
| day | Yes | - |
| hour | No | 0 |
| minute | No | 0 |
| second | No | 0 |
| microsecond | No | 0 |

---

## strftime() Method

Format date objects into readable strings.

```python
import datetime

x = datetime.datetime(2018, 6, 1)
print(x.strftime("%B"))  # Output: June
```

### Common Format Codes

| Code | Description | Example |
|------|-------------|---------|
| `%Y` | Year (4 digits) | 2018 |
| `%y` | Year (2 digits) | 18 |
| `%m` | Month (01-12) | 06 |
| `%B` | Month name (full) | June |
| `%b` | Month name (short) | Jun |
| `%d` | Day (01-31) | 01 |
| `%A` | Weekday (full) | Friday |
| `%a` | Weekday (short) | Fri |
| `%H` | Hour (00-23) | 14 |
| `%I` | Hour (01-12) | 02 |
| `%M` | Minute (00-59) | 30 |
| `%S` | Second (00-59) | 45 |

---

# Python Math

## Built-in Math Functions

### min() and max()
```python
x = min(5, 10, 25)  # Output: 5
y = max(5, 10, 25)  # Output: 25
```

### abs()
```python
x = abs(-7.25)  # Output: 7.25
```

### pow()
```python
x = pow(4, 3)  # Output: 64 (4³)
```

---

## Math Module

Import `math` module for advanced mathematical functions.

```python
import math
```

### Common Math Functions

| Function | Description | Example |
|----------|-------------|---------|
| `math.sqrt(x)` | Square root | `math.sqrt(64)` → 8.0 |
| `math.ceil(x)` | Round up | `math.ceil(1.4)` → 2 |
| `math.floor(x)` | Round down | `math.floor(1.4)` → 1 |
| `math.pi` | Pi constant | 3.14159... |
| `math.e` | Euler's number | 2.71828... |

### Examples
```python
import math

print(math.sqrt(64))    # 8.0
print(math.ceil(1.4))   # 2
print(math.floor(1.4))  # 1
print(math.pi)          # 3.141592653589793
```

---

## Quick Reference

### Module Import
```python
import module_name
from module_name import item
import module_name as alias
```

### Datetime
```python
import datetime
now = datetime.datetime.now()
formatted = now.strftime("%Y-%m-%d")
```

### Math
```python
import math
result = math.sqrt(16)  # 4.0
```

---

## Key Takeaways

### ✅ Remember
- **Module** = code library in .py file
- **import** to use modules
- **from import** for specific items
- **as** for aliases
- **dir()** lists module contents
- **datetime** for date/time operations
- **strftime()** formats dates
- **math** module for advanced math
- **Built-in functions:** min, max, abs, pow

### 🎯 Interview Important
- Difference between import and from import
- Module naming conventions
- Common built-in modules
- datetime formatting codes
- Math module vs built-in functions

---

**Use modules to organize code and access powerful built-in functionality!**