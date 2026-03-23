# Python Variables

## What are Variables?

Variables are **containers for storing data values**.

Think of a variable like a **box with a label** - you can put different things inside and change the contents anytime.

---

## Creating Variables

### No Declaration Needed
Python has **no command for declaring a variable**. A variable is created when you **first assign a value** to it.

```python
x = 5
y = "John"
print(x)  # Output: 5
print(y)  # Output: John
```

### Variables Can Change Type
Variables can **change type** after they are created:

```python
x = 4        # x is a number
x = "Sally"  # Now x is text
print(x)     # Output: Sally
```

---

## Data Type Casting

You can **specify the data type** using casting:

```python
x = str(3)    # x will be '3' (text)
y = int(3)    # y will be 3 (number)
z = float(3)  # z will be 3.0 (decimal)

print(x)  # Output: '3'
print(y)  # Output: 3
print(z)  # Output: 3.0
```

### Get Variable Type
Use `type()` to check what type a variable is:

```python
x = 5
y = "John"
print(type(x))  # Output: <class 'int'>
print(type(y))  # Output: <class 'str'>
```

---

## Quotes for Text

Text variables can use **single or double quotes**:

```python
x = "John"
# Same as:
x = 'John'
```

Both work exactly the same way.

---

## Case Sensitivity

Variable names are **case-sensitive**:

```python
a = 4
A = "Sally"
# These are TWO DIFFERENT variables!
print(a)  # Output: 4
print(A)  # Output: Sally
```

---

## Variable Naming Rules

### ✅ Valid Names
```python
myvar = "John"
my_var = "John"
_my_var = "John"
myVar = "John"
MYVAR = "John"
myvar2 = "John"
```

### ❌ Invalid Names
```python
2myvar = "John"    # Can't start with number
my-var = "John"    # Can't use dash
my var = "John"    # Can't have spaces
```

### Rules Summary
1. Must start with **letter** or **underscore** (_)
2. Cannot start with a **number**
3. Can only contain **letters, numbers, and underscores**
4. **Case-sensitive**
5. Cannot be Python **keywords** (like `if`, `for`, `while`)

---

## Assign Multiple Values

### Multiple Variables, Multiple Values
```python
x, y, z = "Orange", "Banana", "Cherry"
print(x)  # Output: Orange
print(y)  # Output: Banana
print(z)  # Output: Cherry
```

**Important:** Number of variables must match number of values!

### One Value to Multiple Variables
```python
x = y = z = "Orange"
print(x)  # Output: Orange
print(y)  # Output: Orange
print(z)  # Output: Orange
```

### Unpack a List
```python
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
print(x)  # Output: apple
print(y)  # Output: banana
print(z)  # Output: cherry
```

---

## Output Variables

### Basic Output
```python
x = "Python is awesome"
print(x)  # Output: Python is awesome
```

### Multiple Variables with Commas
```python
x = "Python"
y = "is"
z = "awesome"
print(x, y, z)  # Output: Python is awesome
```

### Using + Operator

#### For Text
```python
x = "Python "
y = "is "
z = "awesome"
print(x + y + z)  # Output: Python is awesome
```

#### For Numbers
```python
x = 5
y = 10
print(x + y)  # Output: 15
```

#### ❌ Mixing Text and Numbers (Error)
```python
x = 5
y = "John"
print(x + y)  # Error! Can't add number and text
```

#### ✅ Correct Way to Mix
```python
x = 5
y = "John"
print(x, y)  # Output: 5 John
```

---

## Global Variables

### What are Global Variables?
Variables created **outside functions** are **global variables**. They can be used **anywhere** in your program.

```python
x = "awesome"  # Global variable

def myfunc():
    print("Python is " + x)  # Can use global variable

myfunc()  # Output: Python is awesome
```

### Local vs Global Variables
```python
x = "awesome"  # Global variable

def myfunc():
    x = "fantastic"  # Local variable (only inside function)
    print("Python is " + x)

myfunc()        # Output: Python is fantastic
print("Python is " + x)  # Output: Python is awesome
```

**Key Point:** Local variables don't change global variables with the same name.

---

## Quick Examples

### Personal Information
```python
name = "Alice"
age = 25
city = "New York"
is_student = True

print("Name:", name)
print("Age:", age)
print("City:", city)
print("Student:", is_student)
```

### Simple Calculator
```python
num1 = 10
num2 = 5
sum_result = num1 + num2
difference = num1 - num2

print("Sum:", sum_result)
print("Difference:", difference)
```

### Shopping List
```python
items = ["milk", "bread", "eggs"]
item1, item2, item3 = items
print("Buy:", item1, item2, item3)
```

---

## Common Mistakes

| Mistake | Problem | Solution |
|---------|---------|----------|
| `2name = "John"` | Starts with number | `name2 = "John"` |
| `my-var = 5` | Uses dash | `my_var = 5` |
| `print(x + y)` | Mixing text + number | `print(x, y)` |
| `Name` vs `name` | Case confusion | Be consistent |

---

## Key Takeaways

### ✅ Remember
- Variables are **containers** for data
- **No declaration** needed - just assign
- Variables can **change type**
- Use **meaningful names**
- **Case-sensitive** naming

### 🎯 Best Practices
- Use **descriptive names**: `student_age` not `x`
- Use **underscores** for multiple words: `first_name`
- Be **consistent** with naming style
- Use **commas** to output multiple variables

---

**Variables are the foundation of programming - master them and you're ready for more advanced concepts!**