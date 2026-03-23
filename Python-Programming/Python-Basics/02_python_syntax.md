# Python Syntax

## Execute Python Syntax

Python code can be executed in two main ways:

### Method 1: Command Line (Interactive Mode)
You can write Python directly in the command line for quick testing:

```python
>>> print("Hello, World!")
Hello, World!
>>> 5 + 3
8
>>> name = "Python"
>>> print(name)
Python
```

**How to access:**
- Windows: Open Command Prompt, type `python`
- Mac/Linux: Open Terminal, type `python3`

### Method 2: Python Files (.py extension)
Create a file with `.py` extension and run it:

**Step 1:** Create a file `myfile.py`
```python
print("Hello, World!")
print("This is my first Python program!")
```

**Step 2:** Run the file
```bash
C:\Users\Your Name>python myfile.py
```

**Output:**
```
Hello, World!
This is my first Python program!
```

---

## Python Indentation

### What is Indentation?
**Indentation** refers to the **spaces at the beginning** of a code line.

### Why Indentation Matters in Python

| Other Languages | Python |
|-----------------|--------|
| Indentation = Readability only | Indentation = **Required syntax** |
| Use `{}` for code blocks | Use **indentation** for code blocks |
| Optional formatting | **Mandatory** formatting |

### Correct Indentation Example
```python
if 5 > 2:
    print("Five is greater than two!")
```

**Output:**
```
Five is greater than two!
```

### ❌ Incorrect Indentation (Error)
```python
if 5 > 2:
print("Five is greater than two!")
```

**Error:**
```
IndentationError: expected an indented block
```

### Indentation Rules

#### Rule 1: At Least One Space
```python
# ✅ Correct - 1 space
if 5 > 2:
 print("Five is greater than two!")

# ✅ Correct - 4 spaces (most common)
if 5 > 2:
    print("Five is greater than two!")

# ✅ Correct - 8 spaces
if 5 > 2:
        print("Five is greater than two!")
```

#### Rule 2: Same Block = Same Indentation
```python
# ✅ Correct - Same indentation in same block
if 5 > 2:
    print("Five is greater than two!")
    print("This is also true!")
```

#### Rule 3: Consistent Spacing
```python
# ❌ Incorrect - Mixed indentation in same block
if 5 > 2:
    print("Five is greater than two!")
        print("Five is greater than two!")  # Different spacing!
```

**Error:**
```
IndentationError: unindent does not match any outer indentation level
```

### Best Practices for Indentation

| Practice | Recommendation | Example |
|----------|----------------|---------|
| **Spaces vs Tabs** | Use 4 spaces | `    print("Hello")` |
| **Consistency** | Same throughout file | All blocks use 4 spaces |
| **Editor Settings** | Configure your editor | Set tab = 4 spaces |

### Nested Indentation Example
```python
if 10 > 5:
    print("10 is greater than 5")
    if 10 > 8:
        print("10 is also greater than 8")
        if 10 == 10:
            print("10 equals 10")
```

**Output:**
```
10 is greater than 5
10 is also greater than 8
10 equals 10
```

---

## Python Variables

### Creating Variables
In Python, a variable is created when you **assign a value** to it:

```python
# Creating variables
x = 5
y = "Hello, World!"
name = "Python"
age = 30
is_student = True
```

### Key Points About Variables

#### No Declaration Command
```python
# ❌ Other languages might require:
# int x;        // C++
# var x;        // JavaScript

# ✅ Python - Direct assignment:
x = 5           # Integer
y = "Hello"     # String
z = 3.14        # Float
```

#### Dynamic Typing
```python
# Same variable can hold different types
x = 5           # x is integer
print(x)        # Output: 5

x = "Hello"     # Now x is string
print(x)        # Output: Hello

x = 3.14        # Now x is float
print(x)        # Output: 3.14
```

### Variable Examples
```python
# Numbers
age = 25
height = 5.9
temperature = -10

# Strings
name = "Alice"
city = "New York"
message = "Welcome to Python!"

# Boolean
is_active = True
is_complete = False

# Using variables
print("Name:", name)
print("Age:", age)
print("Height:", height)
print("Active:", is_active)
```

**Output:**
```
Name: Alice
Age: 25
Height: 5.9
Active: True
```

---

## Comments

### What are Comments?
Comments are used for **in-code documentation** and explanations. They help other programmers (and yourself) understand the code.

### Single Line Comments
Comments start with `#` symbol:

```python
# This is a comment
print("Hello, World!")

# Calculate the area of rectangle
length = 10
width = 5
area = length * width  # This calculates area
print("Area:", area)
```

### Comment Examples

#### Explaining Code
```python
# Get user input
name = input("Enter your name: ")

# Check if name is not empty
if name:
    print("Hello,", name)  # Greet the user
else:
    print("No name provided")  # Handle empty input
```

#### Documenting Variables
```python
# Student information
student_name = "John Doe"      # Full name of student
student_age = 20               # Age in years
student_grade = 85.5           # Grade percentage
is_passed = True               # Pass/fail status
```

#### Temporary Code Disabling
```python
print("This line will run")
# print("This line is commented out")
print("This line will also run")
```

### Multi-line Comments (Workaround)
Python doesn't have official multi-line comments, but you can use multiple `#`:

```python
# This is a multi-line comment
# that spans across multiple lines
# to explain complex logic
print("Hello, World!")
```

### Comment Best Practices

| Do ✅ | Don't ❌ |
|-------|----------|
| Explain **why**, not **what** | `x = 5  # Set x to 5` |
| Use clear, concise language | Write novels in comments |
| Update comments with code changes | Leave outdated comments |
| Comment complex logic | Comment obvious code |

#### Good Comments
```python
# Calculate compound interest for investment planning
principal = 1000
rate = 0.05
time = 10

# Using compound interest formula: A = P(1 + r)^t
amount = principal * (1 + rate) ** time
```

#### Poor Comments
```python
# Set x to 5
x = 5

# Print x
print(x)
```

---

## Putting It All Together

Here's a complete example combining syntax, indentation, variables, and comments:

```python
# Student Grade Calculator
# This program calculates final grades for students

# Student information
student_name = "Alice Johnson"
math_score = 85
science_score = 92
english_score = 78

# Calculate average score
total_score = math_score + science_score + english_score
average_score = total_score / 3

# Display results with proper indentation
print("Student Grade Report")
print("=" * 20)  # Print separator line

if average_score >= 90:
    print("Grade: A")
    print("Excellent work!")
elif average_score >= 80:
    print("Grade: B")
    print("Good job!")
elif average_score >= 70:
    print("Grade: C")
    print("Satisfactory")
else:
    print("Grade: F")
    print("Needs improvement")

# Final summary
print(f"Student: {student_name}")
print(f"Average Score: {average_score:.1f}")
```

---

## Key Takeaways

### 1. **Execution Methods**
- Interactive mode for testing
- File execution for programs

### 2. **Indentation is Crucial**
- Use 4 spaces (recommended)
- Be consistent within blocks
- Python enforces proper indentation

### 3. **Variables are Simple**
- No declaration needed
- Dynamic typing
- Assign and use immediately

### 4. **Comments Improve Code**
- Use `#` for single-line comments
- Explain complex logic
- Keep comments updated

---

## Common Beginner Mistakes

| Mistake | Problem | Solution |
|---------|---------|----------|
| **No Indentation** | `IndentationError` | Add proper spaces |
| **Mixed Indentation** | `IndentationError` | Use consistent spacing |
| **Forgetting Comments** | Hard to understand code | Add explanatory comments |
| **Over-commenting** | Cluttered code | Comment only when necessary |

---

## Next Steps

Now that you understand Python syntax basics, you're ready to learn:
1. **Data Types** (strings, numbers, booleans)
2. **Operators** (arithmetic, comparison, logical)
3. **Input/Output** operations
4. **Control Structures** (if/else, loops)

---

**Remember**: Python's strength lies in its **simplicity and readability**. Master these syntax fundamentals, and you'll have a solid foundation for all Python programming!