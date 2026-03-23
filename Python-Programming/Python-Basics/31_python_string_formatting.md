# Python String Formatting

## What is String Formatting?

**Definition:** String formatting allows you to insert variables and expressions into strings.

**Modern Way:** F-strings (Python 3.6+) - preferred method
**Old Way:** format() method (before Python 3.6)

---

## F-Strings (Recommended)

**Syntax:** Put `f` in front of the string literal and use `{}` for placeholders.

### Basic F-String
```python
txt = f"The price is 49 dollars"
print(txt)  # Output: The price is 49 dollars
```

### With Variables
```python
price = 59
txt = f"The price is {price} dollars"
print(txt)  # Output: The price is 59 dollars
```

---

## Placeholders and Modifiers

### Basic Placeholder
```python
name = "Alice"
age = 25
txt = f"My name is {name} and I am {age} years old"
print(txt)  # Output: My name is Alice and I am 25 years old
```

### With Modifiers
Use `:` followed by formatting type.

```python
price = 59
txt = f"The price is {price:.2f} dollars"
print(txt)  # Output: The price is 59.00 dollars
```

### Direct Values
```python
txt = f"The price is {95:.2f} dollars"
print(txt)  # Output: The price is 95.00 dollars
```

---

## Operations in F-Strings

### Math Operations
```python
txt = f"The price is {20 * 59} dollars"
print(txt)  # Output: The price is 1180 dollars
```

### Variables with Operations
```python
price = 59
tax = 0.25
txt = f"The price is {price + (price * tax)} dollars"
print(txt)  # Output: The price is 73.75 dollars
```

### Conditional Expressions
```python
price = 49
txt = f"It is very {'Expensive' if price > 50 else 'Cheap'}"
print(txt)  # Output: It is very Cheap
```

---

## Functions in F-Strings

### Built-in Methods
```python
fruit = "apples"
txt = f"I love {fruit.upper()}"
print(txt)  # Output: I love APPLES
```

### Custom Functions
```python
def myconverter(x):
    return x * 0.3048

txt = f"The plane is flying at a {myconverter(30000)} meter altitude"
print(txt)  # Output: The plane is flying at a 9144.0 meter altitude
```

---

## Formatting Types

| Type | Description | Example | Output |
|------|-------------|---------|--------|
| `:.2f` | 2 decimal places | `f"{3.14159:.2f}"` | 3.14 |
| `:,` | Thousand separator | `f"{59000:,}"` | 59,000 |
| `:_` | Underscore separator | `f"{59000:_}"` | 59_000 |
| `:.2%` | Percentage | `f"{0.25:.2%}"` | 25.00% |
| `:>10` | Right align (width 10) | `f"{'hi':>10}"` | "        hi" |
| `:<10` | Left align (width 10) | `f"{'hi':<10}"` | "hi        " |
| `:^10` | Center align (width 10) | `f"{'hi':^10}"` | "    hi    " |

---

## Common Formatting Examples

### Numbers
```python
price = 59000
print(f"Price: {price:,}")           # Price: 59,000
print(f"Price: {price:.2f}")         # Price: 59000.00
print(f"Price: ${price:,.2f}")       # Price: $59,000.00
```

### Percentages
```python
rate = 0.1234
print(f"Rate: {rate:.2%}")           # Rate: 12.34%
```

### Alignment
```python
name = "Alice"
print(f"|{name:<10}|")               # |Alice     |
print(f"|{name:>10}|")               # |     Alice|
print(f"|{name:^10}|")               # |  Alice   |
```

### Padding with Zeros
```python
number = 42
print(f"{number:05}")                # 00042
```

---

## format() Method (Legacy)

**Note:** Still works but f-strings are preferred.

### Basic format()
```python
price = 49
txt = "The price is {} dollars"
print(txt.format(price))  # Output: The price is 49 dollars
```

### With Formatting
```python
price = 49
txt = "The price is {:.2f} dollars"
print(txt.format(price))  # Output: The price is 49.00 dollars
```

### Multiple Values
```python
quantity = 3
itemno = 567
price = 49
myorder = "I want {} pieces of item number {} for {:.2f} dollars."
print(myorder.format(quantity, itemno, price))
# Output: I want 3 pieces of item number 567 for 49.00 dollars.
```

---

## Index Numbers with format()

### Positional Arguments
```python
quantity = 3
itemno = 567
price = 49
myorder = "I want {0} pieces of item number {1} for {2:.2f} dollars."
print(myorder.format(quantity, itemno, price))
```

### Reusing Values
```python
age = 36
name = "John"
txt = "His name is {1}. {1} is {0} years old."
print(txt.format(age, name))
# Output: His name is John. John is 36 years old.
```

---

## Named Indexes with format()

```python
myorder = "I have a {carname}, it is a {model}."
print(myorder.format(carname="Ford", model="Mustang"))
# Output: I have a Ford, it is a Mustang.
```

---

## F-Strings vs format() Comparison

| Feature | F-String | format() |
|---------|----------|----------|
| **Syntax** | `f"Hello {name}"` | `"Hello {}".format(name)` |
| **Performance** | Faster | Slower |
| **Readability** | More readable | Less readable |
| **Python Version** | 3.6+ | All versions |
| **Expressions** | `f"{x + y}"` | `"{}".format(x + y)` |

---

## Advanced F-String Examples

### Date Formatting
```python
from datetime import datetime

now = datetime.now()
print(f"Today is {now:%Y-%m-%d}")     # Today is 2026-03-23
print(f"Time is {now:%H:%M:%S}")      # Time is 14:30:45
```

### Dictionary Access
```python
person = {"name": "Alice", "age": 25}
print(f"Name: {person['name']}, Age: {person['age']}")
# Output: Name: Alice, Age: 25
```

### List Access
```python
colors = ["red", "green", "blue"]
print(f"First color: {colors[0]}")    # First color: red
```

### Method Chaining
```python
text = "hello world"
print(f"Formatted: {text.title().replace(' ', '-')}")
# Output: Formatted: Hello-World
```

---

## Practical Examples

### Report Generation
```python
name = "Alice"
score = 87.5
grade = "B+"
report = f"""
Student Report
==============
Name: {name}
Score: {score:.1f}%
Grade: {grade}
Status: {'Pass' if score >= 60 else 'Fail'}
"""
print(report)
```

### Price Calculator
```python
def calculate_total(price, tax_rate, discount=0):
    tax = price * tax_rate
    total = price + tax - discount
    return f"""
    Price: ${price:.2f}
    Tax ({tax_rate:.1%}): ${tax:.2f}
    Discount: ${discount:.2f}
    Total: ${total:.2f}
    """

print(calculate_total(100, 0.08, 10))
```

---

## Quick Reference

### F-String Basics
```python
f"Hello {name}"                    # Variable
f"Result: {x + y}"                 # Expression
f"Price: {price:.2f}"              # 2 decimals
f"Count: {count:,}"                # Thousand separator
f"Text: {text:>10}"                # Right align
```

### Common Patterns
```python
# Currency
f"${amount:,.2f}"                  # $1,234.56

# Percentage
f"{rate:.1%}"                      # 12.3%

# Padding
f"{number:05d}"                    # 00123

# Date
f"{date:%Y-%m-%d}"                 # 2026-03-23
```

---

## Key Takeaways

### ✅ Remember
- **F-strings** are the modern, preferred way (Python 3.6+)
- **Placeholders** use `{}` with variables/expressions
- **Modifiers** use `:` for formatting (decimals, alignment, etc.)
- **Operations** can be performed inside placeholders
- **Functions** can be called inside placeholders
- **format()** method still works but is slower
- **F-strings** are faster and more readable

### 🎯 Interview Important
- F-strings vs format() method differences
- Common formatting types (:.2f, :,, :%, etc.)
- How to perform operations in f-strings
- Alignment and padding options
- When to use f-strings vs other methods
- Performance benefits of f-strings

---

**Use f-strings for clean, readable, and efficient string formatting!**