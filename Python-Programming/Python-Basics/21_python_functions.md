# Python Functions

## What is a Function?

**Definition:** A function is a reusable block of code that only runs when it is called.

### Why Use Functions?

| Without Functions | With Functions |
|-------------------|----------------|
| Repetitive code | Write once, use many times |
| Hard to maintain | Easy to update |
| More errors | Less errors |
| Longer code | Shorter code |

---

## Creating a Function

**Syntax:**
```python
def function_name():
    statement
```

Use the `def` keyword followed by function name and parentheses.

### Example
```python
def my_function():
    print("Hello from a function")
```

**Important:** Code inside the function must be indented.

---

## Calling a Function

**Definition:** To execute a function, write its name followed by parentheses.

```python
def my_function():
    print("Hello from a function")

my_function()
# Output: Hello from a function
```

### Calling Multiple Times
```python
def my_function():
    print("Hello from a function")

my_function()
my_function()
my_function()

# Output:
# Hello from a function
# Hello from a function
# Hello from a function
```

---

## Function Names

Function names follow the same rules as variable names:

| Rule | Description | Example |
|------|-------------|---------|
| Start with letter/underscore | Must begin with a-z, A-Z, or _ | `calculate_sum()` |
| Letters, numbers, underscores | Can contain a-z, A-Z, 0-9, _ | `my_function2()` |
| Case-sensitive | Different cases = different names | `myFunc` ≠ `myfunc` |

### Valid Function Names
```python
calculate_sum()
_private_function()
myFunction2()
get_user_data()
```

**Best Practice:** Use descriptive names that explain what the function does.


## Why Use Functions? - Practical Example

### Without Functions (Repetitive)
```python
# Converting temperatures - repetitive code
temp1 = 77
celsius1 = (temp1 - 32) * 5 / 9
print(celsius1)

temp2 = 95
celsius2 = (temp2 - 32) * 5 / 9
print(celsius2)

temp3 = 50
celsius3 = (temp3 - 32) * 5 / 9
print(celsius3)
```

### With Functions (Reusable)
```python
# Converting temperatures - reusable code
def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5 / 9

print(fahrenheit_to_celsius(77))
print(fahrenheit_to_celsius(95))
print(fahrenheit_to_celsius(50))
```

---

## Return Values

**Definition:** Functions can send data back using the `return` statement.

### Basic Return
```python
def get_greeting():
    return "Hello from a function"

message = get_greeting()
print(message)
# Output: Hello from a function
```

### Using Return Value Directly
```python
def get_greeting():
    return "Hello from a function"

print(get_greeting())
# Output: Hello from a function
```

### No Return Statement
If a function doesn't have a return statement, it returns `None` by default.

```python
def my_function():
    print("Hello")

result = my_function()
print(result)
# Output:
# Hello
# None
```

---

## The Pass Statement

**Definition:** Function definitions cannot be empty. Use `pass` as a placeholder.

```python
def my_function():
    pass
```

**Use Case:** When developing, define structure first, implement later.

```python
def calculate_tax():
    pass  # TODO: Implement tax calculation

def process_payment():
    pass  # TODO: Implement payment processing
```


## Function Arguments

**Definition:** Information passed into functions as arguments.

### Syntax
```python
def function_name(parameter):
    statement
```

### Example
```python
def my_function(fname):
    print(fname + " Refsnes")

my_function("Emil")
my_function("Tobias")
my_function("Linus")

# Output:
# Emil Refsnes
# Tobias Refsnes
# Linus Refsnes
```

---

## Parameters vs Arguments

| Term | Definition | Location |
|------|------------|----------|
| **Parameter** | Variable in function definition | `def my_function(name):` |
| **Argument** | Actual value passed to function | `my_function("Emil")` |

### Example
```python
def my_function(name):  # name is a parameter
    print("Hello", name)

my_function("Emil")  # "Emil" is an argument
```

---

## Number of Arguments

**Rule:** Function must be called with the correct number of arguments.

### Correct Number
```python
def my_function(fname, lname):
    print(fname + " " + lname)

my_function("Emil", "Refsnes")
# Output: Emil Refsnes
```

### Wrong Number (Error)
```python
def my_function(fname, lname):
    print(fname + " " + lname)

my_function("Emil")  # Error! Missing 1 argument
```

---

## Default Parameter Values

**Definition:** Assign default values to parameters. If no argument is passed, the default is used.

```python
def my_function(name="friend"):
    print("Hello", name)

my_function("Emil")    # Output: Hello Emil
my_function("Tobias")  # Output: Hello Tobias
my_function()          # Output: Hello friend
my_function("Linus")   # Output: Hello Linus
```

### Another Example
```python
def my_function(country="Norway"):
    print("I am from", country)

my_function("Sweden")  # Output: I am from Sweden
my_function("India")   # Output: I am from India
my_function()          # Output: I am from Norway
my_function("Brazil")  # Output: I am from Brazil
```


## Keyword Arguments

**Definition:** Send arguments with `key = value` syntax. Order doesn't matter.

### Example
```python
def my_function(animal, name):
    print("I have a", animal)
    print("My", animal + "'s name is", name)

my_function(animal="dog", name="Buddy")
# Output:
# I have a dog
# My dog's name is Buddy
```

### Order Doesn't Matter
```python
def my_function(animal, name):
    print("I have a", animal)
    print("My", animal + "'s name is", name)

my_function(name="Buddy", animal="dog")
# Output:
# I have a dog
# My dog's name is Buddy
```

**Note:** Often shortened to **kwargs** in documentation.

---

## Positional Arguments

**Definition:** Arguments passed without keywords. Order matters.

```python
def my_function(animal, name):
    print("I have a", animal)
    print("My", animal + "'s name is", name)

my_function("dog", "Buddy")
# Output:
# I have a dog
# My dog's name is Buddy
```

### Order Matters
```python
def my_function(animal, name):
    print("I have a", animal)
    print("My", animal + "'s name is", name)

my_function("Buddy", "dog")
# Output:
# I have a Buddy
# My Buddy's name is dog
```

---

## Mixing Positional and Keyword Arguments

**Rule:** Positional arguments must come before keyword arguments.

```python
def my_function(animal, name, age):
    print("I have a", age, "year old", animal, "named", name)

my_function("dog", name="Buddy", age=5)
# Output: I have a 5 year old dog named Buddy
```


## Passing Different Data Types

You can pass any data type as an argument (string, number, list, dictionary, etc.).

### Passing a List
```python
def my_function(fruits):
    for fruit in fruits:
        print(fruit)

my_fruits = ["apple", "banana", "cherry"]
my_function(my_fruits)

# Output:
# apple
# banana
# cherry
```

### Passing a Dictionary
```python
def my_function(person):
    print("Name:", person["name"])
    print("Age:", person["age"])

my_person = {"name": "Emil", "age": 25}
my_function(my_person)

# Output:
# Name: Emil
# Age: 25
```

---

## Return Values with Arguments

```python
def my_function(x, y):
    return x + y

result = my_function(5, 3)
print(result)
# Output: 8
```

### Returning Different Data Types

#### Return a List
```python
def my_function():
    return ["apple", "banana", "cherry"]

fruits = my_function()
print(fruits[0])  # Output: apple
print(fruits[1])  # Output: banana
print(fruits[2])  # Output: cherry
```

#### Return a Tuple
```python
def my_function():
    return (10, 20)

x, y = my_function()
print("x:", x)  # Output: x: 10
print("y:", y)  # Output: y: 20
```

---

## Positional-Only Arguments

**Definition:** Specify that a function can have ONLY positional arguments using `, /`.

### With `, /`
```python
def my_function(name, /):
    print("Hello", name)

my_function("Emil")  # Works
# my_function(name="Emil")  # Error!
```

### Without `, /`
```python
def my_function(name):
    print("Hello", name)

my_function("Emil")        # Works
my_function(name="Emil")   # Also works
```


## Keyword-Only Arguments

**Definition:** Specify that a function can have ONLY keyword arguments using `*, `.

### With `*, `
```python
def my_function(*, name):
    print("Hello", name)

my_function(name="Emil")  # Works
# my_function("Emil")  # Error!
```

### Without `*, `
```python
def my_function(name):
    print("Hello", name)

my_function("Emil")        # Works
my_function(name="Emil")   # Also works
```

---

## Combining Positional-Only and Keyword-Only

Arguments before `/` are positional-only, arguments after `*` are keyword-only.

```python
def my_function(a, b, /, *, c, d):
    return a + b + c + d

result = my_function(5, 10, c=15, d=20)
print(result)
# Output: 50
```

| Position | Type | Example |
|----------|------|---------|
| Before `/` | Positional-only | `a, b` |
| After `*` | Keyword-only | `c, d` |

---

## Arbitrary Arguments - *args

**Definition:** Use `*args` when you don't know how many arguments will be passed.

### Syntax
```python
def my_function(*args):
    statement
```

### Example
```python
def my_function(*kids):
    print("The youngest child is " + kids[2])

my_function("Emil", "Tobias", "Linus")
# Output: The youngest child is Linus
```

---

## What is *args?

`*args` allows a function to accept any number of positional arguments. Inside the function, `args` becomes a tuple.

```python
def my_function(*args):
    print("Type:", type(args))
    print("First argument:", args[0])
    print("Second argument:", args[1])
    print("All arguments:", args)

my_function("Emil", "Tobias", "Linus")

# Output:
# Type: <class 'tuple'>
# First argument: Emil
# Second argument: Tobias
# All arguments: ('Emil', 'Tobias', 'Linus')
```


## Using *args with Regular Arguments

Regular parameters must come before `*args`.

```python
def my_function(greeting, *names):
    for name in names:
        print(greeting, name)

my_function("Hello", "Emil", "Tobias", "Linus")

# Output:
# Hello Emil
# Hello Tobias
# Hello Linus
```

---

## Practical Examples with *args

### Sum of Any Number of Values
```python
def my_function(*numbers):
    total = 0
    for num in numbers:
        total += num
    return total

print(my_function(1, 2, 3))           # Output: 6
print(my_function(10, 20, 30, 40))    # Output: 100
print(my_function(5))                 # Output: 5
```

### Find Maximum Value
```python
def my_function(*numbers):
    if len(numbers) == 0:
        return None
    max_num = numbers[0]
    for num in numbers:
        if num > max_num:
            max_num = num
    return max_num

print(my_function(3, 7, 2, 9, 1))
# Output: 9
```

---

## Arbitrary Keyword Arguments - **kwargs

**Definition:** Use `**kwargs` when you don't know how many keyword arguments will be passed.

### Syntax
```python
def my_function(**kwargs):
    statement
```

### Example
```python
def my_function(**kid):
    print("His last name is " + kid["lname"])

my_function(fname="Tobias", lname="Refsnes")
# Output: His last name is Refsnes
```

---

## What is **kwargs?

`**kwargs` allows a function to accept any number of keyword arguments. Inside the function, `kwargs` becomes a dictionary.

```python
def my_function(**myvar):
    print("Type:", type(myvar))
    print("Name:", myvar["name"])
    print("Age:", myvar["age"])
    print("All data:", myvar)

my_function(name="Tobias", age=30, city="Bergen")

# Output:
# Type: <class 'dict'>
# Name: Tobias
# Age: 30
# All data: {'name': 'Tobias', 'age': 30, 'city': 'Bergen'}
```


## Using **kwargs with Regular Arguments

Regular parameters must come before `**kwargs`.

```python
def my_function(username, **details):
    print("Username:", username)
    print("Additional details:")
    for key, value in details.items():
        print("  ", key + ":", value)

my_function("emil123", age=25, city="Oslo", hobby="coding")

# Output:
# Username: emil123
# Additional details:
#    age: 25
#    city: Oslo
#    hobby: coding
```

---

## Combining *args and **kwargs

You can use both in the same function. Order must be:
1. Regular parameters
2. `*args`
3. `**kwargs`

```python
def my_function(title, *args, **kwargs):
    print("Title:", title)
    print("Positional arguments:", args)
    print("Keyword arguments:", kwargs)

my_function("User Info", "Emil", "Tobias", age=25, city="Oslo")

# Output:
# Title: User Info
# Positional arguments: ('Emil', 'Tobias')
# Keyword arguments: {'age': 25, 'city': 'Oslo'}
```

---

## Unpacking Arguments

Use `*` and `**` operators when calling functions to unpack lists or dictionaries.

### Unpacking Lists with *
```python
def my_function(a, b, c):
    return a + b + c

numbers = [1, 2, 3]
result = my_function(*numbers)  # Same as: my_function(1, 2, 3)
print(result)
# Output: 6
```

### Unpacking Dictionaries with **
```python
def my_function(fname, lname):
    print("Hello", fname, lname)

person = {"fname": "Emil", "lname": "Refsnes"}
my_function(**person)  # Same as: my_function(fname="Emil", lname="Refsnes")

# Output: Hello Emil Refsnes
```

**Remember:**
- Use `*` and `**` in function **definitions** to collect arguments
- Use `*` and `**` in function **calls** to unpack arguments


## Variable Scope

**Definition:** A variable is only available from inside the region where it's created.

### Local Scope

**Definition:** A variable created inside a function belongs to the local scope.

```python
def myfunc():
    x = 300
    print(x)

myfunc()
# Output: 300
```

Variable `x` is not available outside the function.

---

## Function Inside Function

Local variables can be accessed from functions within the function.

```python
def myfunc():
    x = 300
    def myinnerfunc():
        print(x)
    myinnerfunc()

myfunc()
# Output: 300
```

---

## Global Scope

**Definition:** A variable created in the main body of code is global and available everywhere.

```python
x = 300

def myfunc():
    print(x)

myfunc()
print(x)

# Output:
# 300
# 300
```

---

## Naming Variables (Local vs Global)

If you use the same variable name inside and outside a function, Python treats them as two separate variables.

```python
x = 300

def myfunc():
    x = 200
    print(x)

myfunc()
print(x)

# Output:
# 200
# 300
```

---

## Global Keyword

**Definition:** Use the `global` keyword to create a global variable from inside a function.

```python
def myfunc():
    global x
    x = 300

myfunc()
print(x)
# Output: 300
```

### Modifying Global Variable
```python
x = 300

def myfunc():
    global x
    x = 200

myfunc()
print(x)
# Output: 200
```


## Nonlocal Keyword

**Definition:** Use `nonlocal` to work with variables in nested functions.

```python
def myfunc1():
    x = "Jane"
    def myfunc2():
        nonlocal x
        x = "hello"
    myfunc2()
    return x

print(myfunc1())
# Output: hello
```

---

## The LEGB Rule

Python searches for variables in this order:

| Order | Scope | Description |
|-------|-------|-------------|
| 1 | **L**ocal | Inside current function |
| 2 | **E**nclosing | Inside enclosing functions |
| 3 | **G**lobal | At top level of module |
| 4 | **B**uilt-in | Python's built-in namespace |

### Example
```python
x = "global"

def outer():
    x = "enclosing"
    def inner():
        x = "local"
        print("Inner:", x)
    inner()
    print("Outer:", x)

outer()
print("Global:", x)

# Output:
# Inner: local
# Outer: enclosing
# Global: global
```

---

## Quick Reference Summary

### Function Definition
```python
def function_name(parameters):
    statement
    return value
```

### Argument Types
| Type | Syntax | Example |
|------|--------|---------|
| Positional | `func(a, b)` | Order matters |
| Keyword | `func(a=1, b=2)` | Order doesn't matter |
| Default | `def func(a=10):` | Optional argument |
| *args | `def func(*args):` | Variable positional |
| **kwargs | `def func(**kwargs):` | Variable keyword |

### Scope Keywords
```python
global x    # Access global variable
nonlocal x  # Access enclosing variable
```


## Key Takeaways

### ✅ Remember
- **Functions** are reusable blocks of code
- **def** keyword defines a function
- **return** sends data back from function
- **pass** is a placeholder for empty functions
- **Parameters** are variables in function definition
- **Arguments** are actual values passed to function
- **Default values** make arguments optional
- **Positional arguments** order matters
- **Keyword arguments** order doesn't matter
- ***args** accepts variable positional arguments (tuple)
- ****kwargs** accepts variable keyword arguments (dict)
- **Local scope** variables only inside function
- **Global scope** variables available everywhere
- **global** keyword modifies global variables
- **nonlocal** keyword modifies enclosing variables
- **LEGB rule** Local → Enclosing → Global → Built-in

### 🎯 Interview Important
- Difference between parameters and arguments
- Difference between *args and **kwargs
- When to use positional vs keyword arguments
- Function scope (local vs global)
- LEGB rule for variable lookup
- How to unpack arguments with * and **
- Default parameter values
- Return vs print in functions
- Positional-only (/) and keyword-only (*) arguments

---

**Master functions to write reusable, organized, and maintainable Python code!**
