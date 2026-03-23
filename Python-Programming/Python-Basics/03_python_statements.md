# Python Statements

## What are Statements?

A **computer program** is a list of "instructions" to be "executed" by a computer.

In a programming language, these programming instructions are called **statements**.

### Simple Statement Example
```python
print("Python is fun!")
```

**Output:**
```
Python is fun!
```

This single line is a **statement** that tells the computer to display text on the screen.

---

## How Statements Work in Python

### Statement Ending
In Python, a **statement usually ends when the line ends**. 

**No semicolon needed!** ✅

| Python | Other Languages |
|--------|-----------------|
| `print("Hello")` | `System.out.println("Hello");` (Java) |
| `x = 5` | `int x = 5;` (C++) |
| `name = "Alice"` | `var name = "Alice";` (JavaScript) |

### Why No Semicolons?
- **Cleaner code** - Less visual clutter
- **Easier to read** - Focus on logic, not syntax
- **Python philosophy** - Simple is better than complex

---

## Multiple Statements

Most Python programs contain **many statements** that are executed **one by one**, in the **same order** as they are written.

### Sequential Execution Example
```python
print("Hello World!")
print("Have a good day.")
print("Learning Python is fun!")
```

**Output:**
```
Hello World!
Have a good day.
Learning Python is fun!
```

### Execution Order Breakdown

| Step | Statement | Action |
|------|-----------|--------|
| 1 | `print("Hello World!")` | Prints "Hello World!" |
| 2 | `print("Have a good day.")` | Prints "Have a good day." |
| 3 | `print("Learning Python is fun!")` | Prints "Learning Python is fun!" |

### More Examples of Sequential Statements

#### Example 1: Variable Operations
```python
name = "Alice"
age = 25
city = "New York"
print("Name:", name)
print("Age:", age)
print("City:", city)
```

**Output:**
```
Name: Alice
Age: 25
City: New York
```

#### Example 2: Mathematical Operations
```python
a = 10
b = 5
sum_result = a + b
difference = a - b
product = a * b
print("Sum:", sum_result)
print("Difference:", difference)
print("Product:", product)
```

**Output:**
```
Sum: 15
Difference: 5
Product: 50
```

---

## Semicolons in Python (Optional, Rarely Used)

### Basic Rule
Semicolons are **optional** in Python and **rarely used**.

### Multiple Statements on One Line
You **can** write multiple statements on one line by separating them with `;`:

```python
print("Hello"); print("How are you?"); print("Bye bye!")
```

**Output:**
```
Hello
How are you?
Bye bye!
```

### Why Semicolons are Rarely Used

| With Semicolons (Hard to Read) | Without Semicolons (Easy to Read) |
|--------------------------------|-----------------------------------|
| `x = 5; y = 10; z = x + y; print(z)` | `x = 5`<br>`y = 10`<br>`z = x + y`<br>`print(z)` |

### Common Semicolon Usage (Rare Cases)
```python
# Quick variable assignments (sometimes used)
x = 1; y = 2; z = 3

# Interactive testing (command line)
>>> a = 5; b = 10; print(a + b)
15
```

---

## Statement Errors

### Missing Separator Error
If you put two statements on the same line **without a separator**, Python gives an error:

#### ❌ Incorrect Code
```python
print("Python is fun!") print("Really!")
```

#### ❌ Error Result
```
SyntaxError: invalid syntax
```

### How to Fix
#### ✅ Option 1: Separate Lines (Recommended)
```python
print("Python is fun!")
print("Really!")
```

#### ✅ Option 2: Use Semicolon
```python
print("Python is fun!"); print("Really!")
```

---

## Best Practices for Statements

### 1. **One Statement Per Line**
```python
# ✅ Good - Easy to read
name = "Alice"
age = 25
print(name)
print(age)

# ❌ Avoid - Hard to read
name = "Alice"; age = 25; print(name); print(age)
```

### 2. **Logical Grouping**
```python
# ✅ Good - Related statements grouped together
# User information
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name

# Display information
print("Welcome,", full_name)
print("Have a great day!")
```

### 3. **Clear Statement Purpose**
```python
# ✅ Good - Each statement has clear purpose
user_input = input("Enter your name: ")
processed_name = user_input.strip().title()
print("Hello,", processed_name)
```

---

## Types of Statements

### 1. **Assignment Statements**
```python
x = 10
name = "Python"
is_active = True
```

### 2. **Print Statements**
```python
print("Hello World")
print("Value of x:", x)
```

### 3. **Input Statements**
```python
user_name = input("Enter your name: ")
user_age = input("Enter your age: ")
```

### 4. **Calculation Statements**
```python
area = length * width
total = price + tax
average = sum_total / count
```

---

## Complete Example: Multiple Statement Types

```python
# Assignment statements
print("=== Student Information System ===")

# Input statements
student_name = input("Enter student name: ")
math_score = int(input("Enter math score: "))
science_score = int(input("Enter science score: "))

# Calculation statements
total_score = math_score + science_score
average_score = total_score / 2

# Print statements
print("\n--- Results ---")
print("Student Name:", student_name)
print("Math Score:", math_score)
print("Science Score:", science_score)
print("Total Score:", total_score)
print("Average Score:", average_score)

# Conditional logic (more statements)
if average_score >= 90:
    print("Grade: A - Excellent!")
elif average_score >= 80:
    print("Grade: B - Good job!")
else:
    print("Grade: C - Keep trying!")
```

---

## Statement Execution Flow

### Linear Execution
```python
print("Step 1: Starting program")    # Executes first
x = 10                               # Executes second
print("Step 2: x =", x)             # Executes third
y = x * 2                            # Executes fourth
print("Step 3: y =", y)             # Executes fifth
print("Step 4: Program complete")   # Executes last
```

**Output:**
```
Step 1: Starting program
Step 2: x = 10
Step 3: y = 20
Step 4: Program complete
```

---

## Key Takeaways

### ✅ **Remember**
1. **Statements are instructions** for the computer
2. **One statement per line** is best practice
3. **No semicolons needed** in Python
4. **Statements execute sequentially** (top to bottom)
5. **Each line ends a statement** automatically

### ❌ **Avoid**
1. Multiple statements on one line
2. Missing separators between statements
3. Unnecessary semicolons
4. Unclear statement purposes

---

## Common Beginner Mistakes

| Mistake | Problem | Solution |
|---------|---------|----------|
| `print("Hi") print("Bye")` | Missing separator | Put on separate lines |
| `x = 5; y = 10; z = 15;` | Unnecessary semicolons | Remove semicolons |
| Complex one-liners | Hard to read | Break into multiple lines |
| No logical grouping | Confusing code | Group related statements |

---

## Next Steps

Now that you understand Python statements, you're ready to learn:
1. **Data Types** (int, float, string, boolean)
2. **Variables** in detail
3. **Operators** (arithmetic, comparison)
4. **Control Flow** (if/else statements)

---

**Remember**: Good code is **readable code**. Write statements that are clear, simple, and easy to understand!