# Python Comments

## What are Comments?

Comments are used to:
- **Explain Python code**
- **Make code more readable**
- **Prevent execution when testing code**

---

## Creating Comments

### Single Line Comments
Comments start with `#`, and Python will **ignore them**:

```python
# This is a comment
print("Hello, World!")
```

**Output:**
```
Hello, World!
```

---

## Comment Placement

### 1. **Above the Code**
```python
# Print a greeting message
print("Hello, World!")

# Calculate the sum
result = 5 + 3
print(result)
```

### 2. **End of Line Comments**
Comments can be placed at the **end of a line**:

```python
print("Hello, World!")  # This is a comment
x = 5  # Store the value 5 in variable x
```

### 3. **Multiple Single Line Comments**
```python
# This program calculates area
# Author: Your Name
# Date: March 2026
length = 10
width = 5
area = length * width
print("Area:", area)
```

---

## Multi-line Comments

Python doesn't have official multi-line comments, but you can use:

### Method 1: Multiple `#` Lines
```python
# This is a multi-line comment
# that explains complex logic
# across several lines
print("Hello, World!")
```

### Method 2: Triple Quotes (Workaround)
```python
"""
This is a multi-line comment
using triple quotes
"""
print("Hello, World!")

'''
You can also use single quotes
for multi-line comments
'''
print("Python is awesome!")
```

---

## Preventing Code Execution

Comments can **prevent Python from executing code**:

### Commenting Out Code
```python
# print("Hello, World!")  # This won't run
print("Cheers, Mate!")    # This will run
```

**Output:**
```
Cheers, Mate!
```

### Temporary Disable Multiple Lines
```python
print("This will run")

# print("This is disabled")
# print("This is also disabled")
# x = 5
# print(x)

print("This will also run")
```

**Output:**
```
This will run
This will also run
```

---

## Comment Best Practices

### ✅ Good Comments
```python
# Calculate compound interest
principal = 1000
rate = 0.05
time = 2
amount = principal * (1 + rate) ** time

# Display user-friendly result
print(f"Final amount: ${amount:.2f}")
```

### ❌ Poor Comments
```python
# Set x to 5
x = 5

# Print x
print(x)
```

---

## Common Comment Patterns

### 1. **Code Sections**
```python
# === USER INPUT ===
name = input("Enter name: ")
age = int(input("Enter age: "))

# === CALCULATIONS ===
birth_year = 2026 - age

# === OUTPUT ===
print(f"{name} was born in {birth_year}")
```

### 2. **TODO Comments**
```python
def calculate_tax(income):
    # TODO: Add different tax brackets
    # TODO: Handle negative income
    return income * 0.2
```

### 3. **Debugging Comments**
```python
x = 10
y = 5
# print("Debug: x =", x, "y =", y)  # Uncomment for debugging
result = x + y
print("Result:", result)
```

---

## Quick Reference

| Comment Type | Syntax | Usage |
|--------------|--------|-------|
| **Single Line** | `# comment` | Explain one line |
| **End of Line** | `code  # comment` | Quick explanation |
| **Multi-line** | `# line1`<br>`# line2` | Detailed explanation |
| **Block Comment** | `""" comment """` | Documentation |
| **Disable Code** | `# code` | Temporary removal |

---

## Practical Example

```python
# Student Grade Calculator
# This program calculates final grades

# Get student information
student_name = input("Enter student name: ")  # Store name
math_score = int(input("Math score: "))       # Convert to integer
science_score = int(input("Science score: ")) # Convert to integer

# Calculate average
total = math_score + science_score  # Sum all scores
average = total / 2                 # Divide by number of subjects

# Determine grade
if average >= 90:
    grade = "A"
elif average >= 80:
    grade = "B"
else:
    grade = "C"

# Display results
print(f"Student: {student_name}")
print(f"Average: {average}")
print(f"Grade: {grade}")

# print("Debug info")  # Disabled for production
```

---

## Key Takeaways

### ✅ **Use Comments For:**
- Explaining **why** code exists
- Describing **complex logic**
- Adding **TODO** notes
- **Temporarily disabling** code

### ❌ **Avoid Comments For:**
- Obvious code explanations
- Outdated information
- Excessive commenting

### 🎯 **Remember:**
- Comments start with `#`
- Python ignores everything after `#`
- Use comments to make code **readable**
- Keep comments **up-to-date** with code changes

---

**Good comments make your code easier to understand and maintain!**