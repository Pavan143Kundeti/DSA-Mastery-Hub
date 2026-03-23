# Python If Statements

## What are If Statements?

**Definition:** An if statement is used to execute code based on whether a condition is True or False.

Python supports logical conditions from mathematics that can be used in if statements:

| Condition | Operator | Example | Description |
|-----------|----------|---------|-------------|
| Equals | `==` | `a == b` | True if a equals b |
| Not Equals | `!=` | `a != b` | True if a not equals b |
| Less than | `<` | `a < b` | True if a less than b |
| Less than or equal | `<=` | `a <= b` | True if a less than or equal to b |
| Greater than | `>` | `a > b` | True if a greater than b |
| Greater than or equal | `>=` | `a >= b` | True if a greater than or equal to b |

---

## Basic If Statement

**Syntax:**
```python
if condition:
    statement
```

### Example
```python
a = 33
b = 200

if b > a:
    print("b is greater than a")
# Output: b is greater than a
```

### How If Statements Work

The if statement evaluates a condition that results in True or False:
- If **True**: Code block inside if statement executes
- If **False**: Code block is skipped

```python
number = 15

if number > 0:
    print("The number is positive")
# Output: The number is positive
```

---

## Indentation

**Definition:** Python uses indentation (whitespace) to define code blocks. This is required for if statements.

### Correct Indentation
```python
a = 33
b = 200

if b > a:
    print("b is greater than a")  # Indented correctly
```

### Incorrect Indentation (Error)
```python
a = 33
b = 200

if b > a:
print("b is greater than a")  # Error! No indentation
```

**Rules:**
- Use spaces or tabs (not both)
- All statements in same block must have same indentation
- Standard is 4 spaces

---

## Multiple Statements in If Block

You can have multiple statements inside an if block. All must be indented at the same level.

```python
age = 20

if age >= 18:
    print("You are an adult")
    print("You can vote")
    print("You have full legal rights")
```

---

## Using Variables in Conditions

### Boolean Variables
```python
is_logged_in = True

if is_logged_in:
    print("Welcome back!")
```

### Truthy and Falsy Values

| Value Type | Example | Evaluates To |
|------------|---------|--------------|
| Zero | `0` | False |
| Empty string | `""` | False |
| None | `None` | False |
| Empty list | `[]` | False |
| Empty dict | `{}` | False |
| Positive number | `5` | True |
| Negative number | `-3` | True |
| Non-empty string | `"hello"` | True |
| Non-empty list | `[1, 2]` | True |

```python
username = "Emil"

if username:  # Non-empty string is True
    print("Username exists")
```

---

## Elif Statement

**Definition:** The `elif` keyword means "if the previous conditions were not true, then try this condition."

### Syntax
```python
if condition1:
    statement1
elif condition2:
    statement2
```

### Example
```python
a = 33
b = 33

if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
# Output: a and b are equal
```

---

## Multiple Elif Statements

You can have as many elif statements as needed. Python checks each condition in order.

```python
score = 75

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
# Output: Grade: C
```

### How Elif Works

| Step | Action |
|------|--------|
| 1 | Evaluate conditions from top to bottom |
| 2 | Execute first True condition |
| 3 | Skip all remaining conditions |

**Important:** Only the first true condition executes, even if multiple conditions are true.

### Example: Age Categories
```python
age = 25

if age < 13:
    print("You are a child")
elif age < 20:
    print("You are a teenager")
elif age < 65:
    print("You are an adult")
elif age >= 65:
    print("You are a senior")
# Output: You are an adult
```

### When to Use Elif

Use elif for **mutually exclusive conditions** (only one can be true at a time).

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
elif day == 5:
    print("Friday")
elif day == 6:
    print("Saturday")
elif day == 7:
    print("Sunday")
# Output: Wednesday
```

---

## Else Statement

**Definition:** The `else` keyword catches anything not caught by preceding conditions. It executes when all previous conditions are False.

### Syntax
```python
if condition1:
    statement1
elif condition2:
    statement2
else:
    statement3
```

### Example
```python
a = 200
b = 33

if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
else:
    print("a is greater than b")
# Output: a is greater than b
```

---

## Else Without Elif

You can use else without elif for simple two-way choices.

```python
a = 200
b = 33

if b > a:
    print("b is greater than a")
else:
    print("b is not greater than a")
# Output: b is not greater than a
```

### How Else Works

- Provides a **default action** when no previous conditions are true
- Acts as a **"catch-all"** for scenarios not covered
- Must come **last** (cannot have elif after else)

### Example: Even or Odd
```python
number = 7

if number % 2 == 0:
    print("The number is even")
else:
    print("The number is odd")
# Output: The number is odd
```

---

## Complete If-Elif-Else Chain

Combine if, elif, and else for comprehensive decision-making.

```python
temperature = 22

if temperature > 30:
    print("It's hot outside!")
elif temperature > 20:
    print("It's warm outside")
elif temperature > 10:
    print("It's cool outside")
else:
    print("It's cold outside!")
# Output: It's warm outside
```

### Else as Fallback

```python
username = "Emil"

if len(username) > 0:
    print(f"Welcome, {username}!")
else:
    print("Error: Username cannot be empty")
# Output: Welcome, Emil!
```

---

## Shorthand If (One-Line)

**Definition:** If you have only one statement, you can write it on the same line.

### Syntax
```python
if condition: statement
```

### Example
```python
a = 5
b = 2

if a > b: print("a is greater than b")
# Output: a is greater than b
```

**Note:** You still need the colon `:` after the condition.

---

## Shorthand If-Else (Ternary Operator)

**Definition:** A conditional expression that assigns a value based on a condition in one line.

### Syntax
```python
value_if_true if condition else value_if_false
```

### Example: Print Statement
```python
a = 2
b = 330

print("A") if a > b else print("B")
# Output: B
```

### Example: Variable Assignment
```python
a = 10
b = 20

bigger = a if a > b else b
print("Bigger is", bigger)
# Output: Bigger is 20
```

### Pattern
```python
variable = value_if_true if condition else value_if_false
```

---

## Multiple Conditions on One Line

You can chain conditional expressions, but keep it readable.

```python
a = 330
b = 330

print("A") if a > b else print("=") if a == b else print("B")
# Output: =
```

---

## Practical Ternary Examples

### Finding Maximum
```python
x = 15
y = 20

max_value = x if x > y else y
print("Maximum value:", max_value)
# Output: Maximum value: 20
```

### Setting Default Value
```python
username = ""

display_name = username if username else "Guest"
print("Welcome,", display_name)
# Output: Welcome, Guest
```

---

## When to Use Shorthand If

| Use Shorthand When | Use Regular If When |
|-------------------|---------------------|
| Condition is simple | Condition is complex |
| Single statement | Multiple statements |
| Quick assignment | Multiple lines of code |
| Improves readability | Complex logic |

---

## Logical Operators in If Statements

**Definition:** Logical operators combine multiple conditions.

| Operator | Description | Example |
|----------|-------------|---------|
| `and` | True if both are True | `a > 5 and b < 10` |
| `or` | True if at least one is True | `a > 5 or b < 10` |
| `not` | Reverses the result | `not a > 5` |

---

## The AND Operator

**Definition:** Both conditions must be True for the entire expression to be True.

```python
a = 200
b = 33
c = 500

if a > b and c > a:
    print("Both conditions are True")
# Output: Both conditions are True
```

### AND Truth Table

| Condition 1 | Condition 2 | Result |
|-------------|-------------|--------|
| True | True | True |
| True | False | False |
| False | True | False |
| False | False | False |

---

## The OR Operator

**Definition:** At least one condition must be True for the entire expression to be True.

```python
a = 200
b = 33
c = 500

if a > b or a > c:
    print("At least one of the conditions is True")
# Output: At least one of the conditions is True
```

### OR Truth Table

| Condition 1 | Condition 2 | Result |
|-------------|-------------|--------|
| True | True | True |
| True | False | True |
| False | True | True |
| False | False | False |

---

## The NOT Operator

**Definition:** Reverses the result of a condition.

```python
a = 33
b = 200

if not a > b:
    print("a is NOT greater than b")
# Output: a is NOT greater than b
```

---

## Combining Multiple Operators

You can combine multiple logical operators. Python evaluates in this order:
1. `not` (first)
2. `and` (second)
3. `or` (third)

```python
age = 25
is_student = False
has_discount_code = True

if (age < 18 or age > 65) and not is_student or has_discount_code:
    print("Discount applies!")
# Output: Discount applies!
```

---

## Using Parentheses for Clarity

Use parentheses to make intentions clear and control evaluation order.

```python
temperature = 25
is_raining = False
is_weekend = True

if (temperature > 20 and not is_raining) or is_weekend:
    print("Great day for outdoor activities!")
# Output: Great day for outdoor activities!
```

---

## More Logical Operator Examples

### User Authentication
```python
username = "Tobias"
password = "secret123"
is_verified = True

if username and password and is_verified:
    print("Login successful")
else:
    print("Login failed")
# Output: Login successful
```

### Range Checking
```python
score = 85

if score >= 0 and score <= 100:
    print("Valid score")
else:
    print("Invalid score")
# Output: Valid score
```

---

## Nested If Statements

**Definition:** If statements inside other if statements.

### Syntax
```python
if condition1:
    if condition2:
        statement
```

### Example
```python
x = 41

if x > 10:
    print("Above ten,")
    if x > 20:
        print("and also above 20!")
    else:
        print("but not above 20.")
# Output:
# Above ten,
# and also above 20!
```

---

## How Nested If Works

Each level creates a deeper level of decision-making. Code evaluates from outermost condition inward.

```python
age = 25
has_license = True

if age >= 18:
    if has_license:
        print("You can drive")
    else:
        print("You need a license")
else:
    print("You are too young to drive")
# Output: You can drive
```

---

## Multiple Levels of Nesting

You can nest multiple levels, but avoid too many for readability.

```python
score = 85
attendance = 90
submitted = True

if score >= 60:
    if attendance >= 80:
        if submitted:
            print("Pass with good standing")
        else:
            print("Pass but missing assignment")
    else:
        print("Pass but low attendance")
else:
    print("Fail")
# Output: Pass with good standing
```

---

## Nested If vs Logical Operators

Sometimes nested if can be simplified using `and`.

### Nested If Approach
```python
temperature = 25
is_sunny = True

if temperature > 20:
    if is_sunny:
        print("Perfect beach weather!")
```

### Logical Operator Approach
```python
temperature = 25
is_sunny = True

if temperature > 20 and is_sunny:
    print("Perfect beach weather!")
```

Both produce the same result. Choose based on:
- **Nested if**: When inner logic is complex or depends on outer condition
- **Logical and**: When both conditions are simple and equally important

---

## More Nested If Examples

### Login Validation
```python
username = "Emil"
password = "python123"
is_active = True

if username:
    if password:
        if is_active:
            print("Login successful")
        else:
            print("Account is not active")
    else:
        print("Password required")
else:
    print("Username required")
# Output: Login successful
```

### Grade Calculation
```python
score = 92
extra_credit = 5

if score >= 90:
    if extra_credit > 0:
        print("A+ grade")
    else:
        print("A grade")
elif score >= 80:
    print("B grade")
else:
    print("C grade or below")
# Output: A+ grade
```

---

## The Pass Statement

**Definition:** A null operation that does nothing when executed. Used as a placeholder.

### Syntax
```python
if condition:
    pass
```

### Example
```python
a = 33
b = 200

if b > a:
    pass
# No error, nothing happens
```

---

## Why Use Pass?

| Reason | Description |
|--------|-------------|
| Placeholder | Code structure created but logic not implemented yet |
| Syntax requirement | Statement required but no action needed |
| Development | Sketch program structure before implementation |
| Future code | Mark where code will be added later |

---

## Pass in Development

```python
age = 16

if age < 18:
    pass  # TODO: Add underage logic later
else:
    print("Access granted")
# Output: Access granted
```

---

## Pass vs Comments

- **Comment**: Ignored by Python
- **Pass**: Actual statement that executes (does nothing)

### This Causes Error
```python
score = 85

if score > 90:
    # This is excellent
# IndentationError: expected an indented block
```

### This Works
```python
score = 85

if score > 90:
    pass  # This is excellent

print("Score processed")
# Output: Score processed
```

---

## Pass with Multiple Conditions

```python
value = 50

if value < 0:
    print("Negative value")
elif value == 0:
    pass  # Zero case - no action needed
else:
    print("Positive value")
# Output: Positive value
```

---

## Pass in Other Contexts

Pass is also used with loops, functions, and classes.

```python
def calculate_discount(price):
    pass  # TODO: Implement discount logic

# Function exists but doesn't do anything yet
```

---

## Quick Reference Summary

### If Statement Structure
```python
if condition:
    statement

if condition:
    statement
elif condition:
    statement
else:
    statement
```

### Shorthand Forms
```python
# One-line if
if condition: statement

# Ternary operator
value = true_value if condition else false_value
```

### Logical Operators
```python
if condition1 and condition2:  # Both must be True
if condition1 or condition2:   # At least one must be True
if not condition:              # Reverse the result
```

### Nested If
```python
if condition1:
    if condition2:
        statement
```

---

## Key Takeaways

### ✅ Remember
- **Indentation** is required and defines code blocks
- **elif** checks additional conditions if previous ones are False
- **else** provides a default action (catch-all)
- **Ternary operator** for simple one-line conditions
- **and** requires both conditions True
- **or** requires at least one condition True
- **not** reverses the condition result
- **pass** is a placeholder that does nothing

### 🎯 Interview Important
- Difference between `and` and `or`
- Operator precedence: `not` > `and` > `or`
- Truthy and Falsy values in Python
- When to use nested if vs logical operators
- Purpose of pass statement
- Ternary operator syntax

---

**Master if statements to control program flow and make decisions in your code!**
