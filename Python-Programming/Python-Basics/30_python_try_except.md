# Python Try Except

## What is Exception Handling?

**Definition:** Exception handling allows you to handle errors gracefully without crashing the program.

**Problem:** When an error occurs, Python normally stops and generates an error message.
**Solution:** Use try-except blocks to catch and handle errors.

---

## Basic Try-Except

### Syntax
```python
try:
    # Code that might cause an error
    statement
except:
    # Code to handle the error
    statement
```

### Example
```python
try:
    print(x)  # x is not defined - will cause error
except:
    print("An exception occurred")

# Output: An exception occurred
```

### Without Try-Except (Program Crashes)
```python
print(x)  # NameError: name 'x' is not defined
```

---

## Try-Except Blocks

| Block | Purpose | When Executed |
|-------|---------|---------------|
| `try` | Test code for errors | Always |
| `except` | Handle the error | Only if error occurs |
| `else` | Execute if no error | Only if no error |
| `finally` | Always execute | Always (cleanup) |

---

## Multiple Except Blocks

Handle different types of errors with specific except blocks.

```python
try:
    print(x)
except NameError:
    print("Variable x is not defined")
except:
    print("Something else went wrong")

# Output: Variable x is not defined
```

### Specific Exception Types
```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
except ValueError:
    print("Invalid value!")
except Exception as e:
    print(f"An error occurred: {e}")
```

---

## Common Exception Types

| Exception | Description | Example |
|-----------|-------------|---------|
| `NameError` | Variable not defined | `print(x)` |
| `ZeroDivisionError` | Division by zero | `10 / 0` |
| `ValueError` | Invalid value | `int("hello")` |
| `TypeError` | Wrong data type | `"hello" + 5` |
| `IndexError` | Index out of range | `list[10]` |
| `KeyError` | Key not found | `dict["missing"]` |
| `FileNotFoundError` | File doesn't exist | `open("missing.txt")` |

---

## Else Block

**Purpose:** Execute code only when no errors occur.

```python
try:
    print("Hello")
except:
    print("Something went wrong")
else:
    print("Nothing went wrong")

# Output:
# Hello
# Nothing went wrong
```

### Practical Example
```python
try:
    file = open("data.txt", "r")
except FileNotFoundError:
    print("File not found!")
else:
    print("File opened successfully")
    content = file.read()
    file.close()
```

---

## Finally Block

**Purpose:** Always executes, regardless of errors. Used for cleanup.

```python
try:
    print(x)
except:
    print("Something went wrong")
finally:
    print("The 'try except' is finished")

# Output:
# Something went wrong
# The 'try except' is finished
```

### File Handling Example
```python
try:
    f = open("demofile.txt")
    try:
        f.write("Hello World")
    except:
        print("Something went wrong when writing to the file")
    finally:
        f.close()  # Always close the file
except:
    print("Something went wrong when opening the file")
```

---

## Raise an Exception

**Purpose:** Manually throw an exception when a condition occurs.

### Basic Raise
```python
x = -1

if x < 0:
    raise Exception("Sorry, no numbers below zero")

# Output: Exception: Sorry, no numbers below zero
```

### Specific Exception Types
```python
x = "hello"

if not type(x) is int:
    raise TypeError("Only integers are allowed")

# Output: TypeError: Only integers are allowed
```

---

## Exception with Details

### Capture Exception Information
```python
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print(f"Error occurred: {e}")
    print(f"Error type: {type(e).__name__}")

# Output:
# Error occurred: division by zero
# Error type: ZeroDivisionError
```

### Multiple Exception Types
```python
try:
    # Some risky code
    value = int(input("Enter a number: "))
    result = 10 / value
except (ValueError, ZeroDivisionError) as e:
    print(f"Invalid input: {e}")
```

---

## Practical Examples

### File Operations
```python
def read_file(filename):
    try:
        with open(filename, 'r') as file:
            return file.read()
    except FileNotFoundError:
        print(f"File '{filename}' not found")
        return None
    except PermissionError:
        print(f"Permission denied to read '{filename}'")
        return None
    except Exception as e:
        print(f"Unexpected error: {e}")
        return None
```

### User Input Validation
```python
def get_integer():
    while True:
        try:
            value = int(input("Enter an integer: "))
            return value
        except ValueError:
            print("Please enter a valid integer!")
```

### Division Calculator
```python
def safe_divide(a, b):
    try:
        result = a / b
        return result
    except ZeroDivisionError:
        print("Error: Cannot divide by zero")
        return None
    except TypeError:
        print("Error: Both arguments must be numbers")
        return None
```

### List Access
```python
def safe_get_item(lst, index):
    try:
        return lst[index]
    except IndexError:
        print(f"Index {index} is out of range")
        return None
    except TypeError:
        print("Index must be an integer")
        return None
```

---

## Best Practices

### Do's
```python
# Be specific with exceptions
try:
    value = int(user_input)
except ValueError:
    print("Invalid number format")

# Use finally for cleanup
try:
    file = open("data.txt")
    # process file
finally:
    file.close()

# Log errors for debugging
import logging
try:
    risky_operation()
except Exception as e:
    logging.error(f"Operation failed: {e}")
```

### Don'ts
```python
# Don't use bare except (too broad)
try:
    risky_code()
except:  # Bad - catches everything
    pass

# Don't ignore exceptions silently
try:
    risky_code()
except:
    pass  # Bad - hides errors

# Don't use exceptions for control flow
try:
    value = my_dict[key]
except KeyError:
    value = default  # Use dict.get(key, default) instead
```

---

## Exception Hierarchy

```
BaseException
 +-- SystemExit
 +-- KeyboardInterrupt
 +-- GeneratorExit
 +-- Exception
      +-- StopIteration
      +-- ArithmeticError
      |    +-- ZeroDivisionError
      +-- LookupError
      |    +-- IndexError
      |    +-- KeyError
      +-- ValueError
      +-- TypeError
      +-- NameError
```

---

## Quick Reference

### Basic Structure
```python
try:
    # risky code
    pass
except SpecificError:
    # handle specific error
    pass
except Exception as e:
    # handle any other error
    print(f"Error: {e}")
else:
    # no error occurred
    pass
finally:
    # always execute (cleanup)
    pass
```

### Common Patterns
```python
# File handling
try:
    with open("file.txt") as f:
        content = f.read()
except FileNotFoundError:
    print("File not found")

# User input
try:
    number = int(input("Enter number: "))
except ValueError:
    print("Invalid number")

# Custom exceptions
if condition:
    raise ValueError("Custom error message")
```

---

## Key Takeaways

### ✅ Remember
- **try** tests code for errors
- **except** handles specific errors
- **else** runs when no errors occur
- **finally** always runs (cleanup)
- **raise** manually throws exceptions
- **Be specific** with exception types
- **Use finally** for cleanup (close files, etc.)
- **Don't ignore** exceptions silently

### 🎯 Interview Important
- Exception handling prevents program crashes
- Difference between except, else, finally
- Common exception types and when they occur
- How to raise custom exceptions
- Best practices for exception handling
- Exception hierarchy in Python
- When to use try-except vs other approaches

---

**Use try-except to handle errors gracefully and make your programs robust!**