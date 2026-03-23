# Python Output / Print

## Print Text

The `print()` function is used to **display text** or **output values** to the screen.

### Basic Print Example
```python
print("Hello World!")
```

**Output:**
```
Hello World!
```

### Multiple Print Statements
You can use the `print()` function **as many times as you want**. Each call prints text on a **new line by default**:

```python
print("Hello World!")
print("I am learning Python.")
print("It is awesome!")
```

**Output:**
```
Hello World!
I am learning Python.
It is awesome!
```

---

## Quotes in Python

### Text Must Be Inside Quotes
Text in Python **must be inside quotes**. You have two options:

| Quote Type | Example | Usage |
|------------|---------|-------|
| **Double Quotes** | `"Hello World"` | Most common |
| **Single Quotes** | `'Hello World'` | Alternative option |

### Correct Quote Usage
```python
print("This will work!")
print('This will also work!')
```

**Output:**
```
This will work!
This will also work!
```

### ❌ Forgetting Quotes (Error)
```python
print(This will cause an error)
```

**Error:**
```
SyntaxError: invalid syntax
```

### When to Use Single vs Double Quotes

#### Use Double Quotes When Text Contains Single Quotes
```python
print("I'm learning Python!")
print("It's a great language!")
```

#### Use Single Quotes When Text Contains Double Quotes
```python
print('He said "Python is awesome!"')
print('The book is called "Learning Python"')
```

#### Mixing Quotes Example
```python
print("Python's print() function is useful")
print('She said "I love Python programming!"')
```

**Output:**
```
Python's print() function is useful
She said "I love Python programming!"
```

---

## Print Without New Line

### Default Behavior
By default, the `print()` function **ends with a new line**:

```python
print("First line")
print("Second line")
print("Third line")
```

**Output:**
```
First line
Second line
Third line
```

### Using the `end` Parameter
To print multiple words on the **same line**, use the `end` parameter:

```python
print("Hello World!", end=" ")
print("I will print on the same line.")
```

**Output:**
```
Hello World! I will print on the same line.
```

### Different `end` Parameter Options

| Parameter | Result | Example |
|-----------|--------|---------|
| `end=" "` | Space between | `Hello World! Next text` |
| `end=""` | No space | `Hello World!Next text` |
| `end="-"` | Custom separator | `Hello World!-Next text` |
| `end="***"` | Multiple characters | `Hello World!***Next text` |

#### Examples of Different `end` Values
```python
print("Python", end=" ")
print("is", end=" ")
print("awesome!")

print("A", end="-")
print("B", end="-")
print("C")

print("Loading", end="")
print(".", end="")
print(".", end="")
print(".")
```

**Output:**
```
Python is awesome!
A-B-C
Loading...
```

---

## Print Numbers

### Basic Number Printing
You can use the `print()` function to **display numbers**:

**Important:** Unlike text, we **don't put numbers inside quotes**:

```python
print(3)
print(358)
print(50000)
```

**Output:**
```
3
358
50000
```

### Numbers vs Text Comparison

| Type | Correct | Incorrect |
|------|---------|-----------|
| **Text** | `print("Hello")` | `print(Hello)` |
| **Numbers** | `print(42)` | `print("42")` ← This is text! |

### Different Number Types
```python
# Integers
print(25)
print(-10)
print(0)

# Floating point numbers
print(3.14)
print(-2.5)
print(0.0)
```

**Output:**
```
25
-10
0
3.14
-2.5
0.0
```

---

## Math Inside Print Function

You can **do math calculations** directly inside the `print()` function:

### Basic Math Operations
```python
print(3 + 3)
print(2 * 5)
print(10 - 4)
print(15 / 3)
```

**Output:**
```
6
10
6
5.0
```

### Complex Math Examples
```python
print(2 + 3 * 4)        # Order of operations: 3*4 first, then +2
print((2 + 3) * 4)      # Parentheses first: 2+3, then *4
print(10 ** 2)          # Exponentiation: 10 squared
print(17 % 5)           # Modulus: remainder of 17 divided by 5
```

**Output:**
```
14
20
100
2
```

### Variables in Math
```python
a = 10
b = 5
print(a + b)
print(a * b)
print(a / b)
```

**Output:**
```
15
50
2.0
```

---

## Mix Text and Numbers

You can **combine text and numbers** in one output by separating them with a **comma**:

### Basic Mixing Example
```python
print("I am", 35, "years old.")
```

**Output:**
```
I am 35 years old.
```

### More Mixing Examples
```python
print("The answer is", 42)
print("Temperature:", 25, "degrees")
print("Score:", 95, "out of", 100)
print("Pi is approximately", 3.14159)
```

**Output:**
```
The answer is 42
Temperature: 25 degrees
Score: 95 out of 100
Pi is approximately 3.14159
```

### Mixing Multiple Data Types
```python
name = "Alice"
age = 25
height = 5.6
is_student = True

print("Name:", name)
print("Age:", age, "years")
print("Height:", height, "feet")
print("Is student:", is_student)
print("Summary:", name, "is", age, "years old and", height, "feet tall")
```

**Output:**
```
Name: Alice
Age: 25 years
Height: 5.6 feet
Is student: True
Summary: Alice is 25 years old and 5.6 feet tall
```

---

## Advanced Print Techniques

### Multiple Items with Custom Separator
```python
print("Apple", "Banana", "Cherry", sep=", ")
print("A", "B", "C", sep="-")
print("Python", "is", "awesome", sep=" >>> ")
```

**Output:**
```
Apple, Banana, Cherry
A-B-C
Python >>> is >>> awesome
```

### Combining `sep` and `end` Parameters
```python
print("First", "Second", "Third", sep="-", end=" | ")
print("Fourth", "Fifth", sep="+")
```

**Output:**
```
First-Second-Third | Fourth+Fifth
```

---

## Common Print Patterns

### 1. **Information Display**
```python
product = "Laptop"
price = 999.99
quantity = 2

print("Product:", product)
print("Price: $", price)
print("Quantity:", quantity)
print("Total: $", price * quantity)
```

### 2. **Progress Indicators**
```python
print("Loading", end="")
for i in range(5):
    print(".", end="")
print(" Complete!")
```

### 3. **Data Tables**
```python
print("Name", "Age", "City", sep=" | ")
print("-" * 20)
print("Alice", 25, "New York", sep=" | ")
print("Bob", 30, "London", sep=" | ")
```

**Output:**
```
Name | Age | City
--------------------
Alice | 25 | New York
Bob | 30 | London
```

---

## Common Mistakes and Solutions

| Mistake | Problem | Solution |
|---------|---------|----------|
| `print(Hello)` | Missing quotes for text | `print("Hello")` |
| `print("5" + 3)` | Mixing text and number | `print(5 + 3)` or `print("5", 3)` |
| `print("Age: " age)` | Missing comma | `print("Age:", age)` |
| Forgetting `end=""` | Unwanted new lines | Use `end=""` parameter |

### Error Examples and Fixes

#### ❌ Wrong Way
```python
print(Hello World)          # Missing quotes
print("Age: " + 25)         # Can't add string and number
print("Result" result)      # Missing comma
```

#### ✅ Correct Way
```python
print("Hello World")        # Quotes added
print("Age:", 25)           # Use comma to separate
print("Result:", result)    # Comma added
```

---

## Practice Examples

### Example 1: Personal Information
```python
name = "John Doe"
age = 28
city = "San Francisco"
salary = 75000

print("=== Personal Information ===")
print("Name:", name)
print("Age:", age, "years old")
print("City:", city)
print("Annual Salary: $", salary)
```

### Example 2: Calculator
```python
num1 = 15
num2 = 7

print("Number 1:", num1)
print("Number 2:", num2)
print("Addition:", num1 + num2)
print("Subtraction:", num1 - num2)
print("Multiplication:", num1 * num2)
print("Division:", num1 / num2)
```

### Example 3: Shopping Receipt
```python
item1 = "Coffee"
price1 = 4.50
item2 = "Sandwich"
price2 = 8.75

print("=== RECEIPT ===")
print(item1, ": $", price1, sep="")
print(item2, ": $", price2, sep="")
print("-" * 15)
print("Total: $", price1 + price2)
```

---

## Key Takeaways

### ✅ **Remember**
1. **Text needs quotes** - `print("Hello")`
2. **Numbers don't need quotes** - `print(42)`
3. **Use commas** to mix text and numbers - `print("Age:", 25)`
4. **Use `end=""` parameter** to avoid new lines
5. **Math works inside print()** - `print(5 + 3)`

### 🎯 **Best Practices**
1. Use **double quotes** for most text
2. Use **single quotes** when text contains double quotes
3. **Separate items with commas** for automatic spacing
4. Use **descriptive text** with your numbers
5. **Group related print statements** together

---

## Next Steps

Now that you understand Python output and printing, you're ready to learn:
1. **Python Input** - Getting data from users
2. **Variables** in more detail
3. **Data Types** (strings, integers, floats)
4. **String Formatting** for advanced output

---

**Remember**: The `print()` function is your **best friend for debugging** and displaying results. Master it well!