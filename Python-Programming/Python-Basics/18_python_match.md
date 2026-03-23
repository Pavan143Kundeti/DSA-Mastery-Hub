# Python Match Statement

## What is Match Statement?

**Definition:** The match statement is used to perform different actions based on different conditions. It's an alternative to writing many if-else statements.

**Note:** Match statement was introduced in Python 3.10.

---

## Why Use Match?

| Instead of Multiple If-Else | Use Match Statement |
|------------------------------|---------------------|
| Many if-elif-else blocks | Single match block |
| Repetitive comparisons | Clean pattern matching |
| Hard to read | Easy to read |
| More code | Less code |

---

## Basic Match Syntax

```python
match expression:
    case x:
        code block
    case y:
        code block
    case z:
        code block
```

### How It Works

| Step | Action |
|------|--------|
| 1 | Match expression is evaluated once |
| 2 | Value compared with each case |
| 3 | If match found, execute that code block |
| 4 | Stop after first match |

---

## Basic Match Example

```python
day = 4

match day:
    case 1:
        print("Monday")
    case 2:
        print("Tuesday")
    case 3:
        print("Wednesday")
    case 4:
        print("Thursday")
    case 5:
        print("Friday")
    case 6:
        print("Saturday")
    case 7:
        print("Sunday")

# Output: Thursday
```

---

## Default Case (Underscore _)

**Definition:** Use underscore `_` as the last case to execute code when no other cases match. It acts as a default case.

### Syntax
```python
match expression:
    case value1:
        code
    case value2:
        code
    case _:
        default code
```

### Example
```python
day = 4

match day:
    case 6:
        print("Today is Saturday")
    case 7:
        print("Today is Sunday")
    case _:
        print("Looking forward to the Weekend")

# Output: Looking forward to the Weekend
```

### Important Rules for Default Case

| Rule | Description |
|------|-------------|
| Always matches | `_` will match any value |
| Must be last | Place as last case |
| Acts as catch-all | Handles all unmatched values |

---

## Combining Values with OR (|)

**Definition:** Use the pipe character `|` as an OR operator to check multiple values in one case.

### Syntax
```python
match expression:
    case value1 | value2 | value3:
        code
```

### Example: Weekday vs Weekend
```python
day = 4

match day:
    case 1 | 2 | 3 | 4 | 5:
        print("Today is a weekday")
    case 6 | 7:
        print("I love weekends!")

# Output: Today is a weekday
```

### More Examples

```python
# Grade classification
grade = 'B'

match grade:
    case 'A' | 'A+':
        print("Excellent!")
    case 'B' | 'B+':
        print("Good job!")
    case 'C' | 'C+':
        print("Average")
    case _:
        print("Need improvement")

# Output: Good job!
```

---

## Guards (If Statements in Cases)

**Definition:** You can add if statements in case evaluation as an extra condition check. These are called guards.

### Syntax
```python
match expression:
    case value if condition:
        code
```

### Example
```python
month = 5
day = 4

match day:
    case 1 | 2 | 3 | 4 | 5 if month == 4:
        print("A weekday in April")
    case 1 | 2 | 3 | 4 | 5 if month == 5:
        print("A weekday in May")
    case _:
        print("No match")

# Output: A weekday in May
```

### More Guard Examples

```python
# Age-based access with additional conditions
age = 16
has_permission = True

match age:
    case age if age >= 18:
        print("Full access")
    case age if age >= 13 and has_permission:
        print("Limited access with permission")
    case _:
        print("No access")

# Output: Limited access with permission
```

---

## Match vs If-Elif-Else

### Using If-Elif-Else
```python
day = 3

if day == 1:
    print("Monday")
elif day == 2:
    print("Tuesday")
elif day == 3:
    print("Wednesday")
elif day == 4:
    print("Thursday")
else:
    print("Other day")
```

### Using Match (Cleaner)
```python
day = 3

match day:
    case 1:
        print("Monday")
    case 2:
        print("Tuesday")
    case 3:
        print("Wednesday")
    case 4:
        print("Thursday")
    case _:
        print("Other day")
```

---

## Comparison Table

| Feature | If-Elif-Else | Match Statement |
|---------|--------------|-----------------|
| Readability | Good | Better |
| Multiple values | Need `or` | Use `\|` |
| Default case | `else` | `_` |
| Guards | Nested if | Built-in with `if` |
| Python version | All versions | 3.10+ |

---

## Practical Examples

### Example 1: HTTP Status Codes
```python
status_code = 404

match status_code:
    case 200:
        print("OK")
    case 201:
        print("Created")
    case 400 | 401 | 403:
        print("Client Error")
    case 404:
        print("Not Found")
    case 500 | 502 | 503:
        print("Server Error")
    case _:
        print("Unknown Status")

# Output: Not Found
```

### Example 2: Menu Selection
```python
choice = 2

match choice:
    case 1:
        print("Starting new game...")
    case 2:
        print("Loading saved game...")
    case 3:
        print("Opening settings...")
    case 4:
        print("Exiting game...")
    case _:
        print("Invalid choice")

# Output: Loading saved game...
```

### Example 3: Traffic Light
```python
light = "yellow"

match light:
    case "green":
        print("Go")
    case "yellow":
        print("Slow down")
    case "red":
        print("Stop")
    case _:
        print("Invalid light color")

# Output: Slow down
```

### Example 4: Season by Month
```python
month = 7

match month:
    case 12 | 1 | 2:
        print("Winter")
    case 3 | 4 | 5:
        print("Spring")
    case 6 | 7 | 8:
        print("Summer")
    case 9 | 10 | 11:
        print("Fall")
    case _:
        print("Invalid month")

# Output: Summer
```

### Example 5: Grade with Guards
```python
score = 85
attendance = 95

match score:
    case s if s >= 90 and attendance >= 90:
        print("A+ (Excellent attendance)")
    case s if s >= 90:
        print("A")
    case s if s >= 80:
        print("B")
    case s if s >= 70:
        print("C")
    case _:
        print("Need improvement")

# Output: B
```

---

## Pattern Matching with Data Structures

### Matching Lists
```python
point = [0, 0]

match point:
    case [0, 0]:
        print("Origin")
    case [0, y]:
        print(f"On Y-axis at {y}")
    case [x, 0]:
        print(f"On X-axis at {x}")
    case [x, y]:
        print(f"Point at ({x}, {y})")

# Output: Origin
```

### Matching Tuples
```python
command = ("move", 10, 20)

match command:
    case ("move", x, y):
        print(f"Moving to ({x}, {y})")
    case ("draw", x, y):
        print(f"Drawing at ({x}, {y})")
    case ("stop",):
        print("Stopping")

# Output: Moving to (10, 20)
```

---

## When to Use Match Statement

| Use Match When | Use If-Elif When |
|----------------|------------------|
| Multiple exact value checks | Complex boolean conditions |
| Pattern matching needed | Range comparisons |
| Cleaner code desired | Python version < 3.10 |
| Working with structured data | Simple two-way decisions |

---

## Important Notes

### Python Version Requirement
```python
# Match statement requires Python 3.10 or higher
# Check your Python version:
import sys
print(sys.version)
```

### Match is Not a Loop
```python
# Match executes only ONE case (first match)
day = 5

match day:
    case 5:
        print("Friday")  # This executes
    case 5:
        print("Also Friday")  # This never executes
```

### No Fall-Through
Unlike switch statements in some languages, Python match doesn't fall through to next case.

---

## Quick Reference

### Basic Structure
```python
match value:
    case pattern1:
        action1
    case pattern2:
        action2
    case _:
        default_action
```

### With OR Operator
```python
match value:
    case 1 | 2 | 3:
        action
```

### With Guards
```python
match value:
    case x if condition:
        action
```

### With Default
```python
match value:
    case specific_value:
        action
    case _:
        default_action
```

---

## Key Takeaways

### ✅ Remember
- **Match statement** introduced in Python 3.10
- **Cleaner alternative** to multiple if-elif-else
- **`_` (underscore)** acts as default case (must be last)
- **`|` (pipe)** combines multiple values (OR operator)
- **Guards** add extra conditions with `if`
- **First match wins** - no fall-through
- **Pattern matching** works with lists, tuples, etc.

### 🎯 Interview Important
- Python version requirement (3.10+)
- Difference between match and if-elif-else
- Purpose of underscore `_` in match
- How to combine multiple values with `|`
- What are guards in match statements
- No fall-through behavior (unlike C/Java switch)

---

**Use match statements for cleaner, more readable code when checking multiple values!**
