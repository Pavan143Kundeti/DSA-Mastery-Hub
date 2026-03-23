# Python Numbers

## Numeric Types in Python

Python has **three numeric types**:

| Type | Description | Example |
|------|-------------|---------|
| `int` | Whole numbers | `1`, `-5`, `1000` |
| `float` | Decimal numbers | `3.14`, `-0.5`, `2.0` |
| `complex` | Complex numbers | `1j`, `3+5j` |

---

## Creating Numeric Variables

Variables of numeric types are created when you **assign a value** to them:

```python
x = 1      # int
y = 2.8    # float
z = 1j     # complex
```

### Verify the Type
Use the `type()` function to check the type:

```python
print(type(x))  # <class 'int'>
print(type(y))  # <class 'float'>
print(type(z))  # <class 'complex'>
```

---

## Integer (int)

**Integer** is a **whole number**, positive or negative, **without decimals**, of **unlimited length**.

### Integer Examples
```python
x = 1
y = 35656222554887711
z = -3255522

print(x)         # Output: 1
print(y)         # Output: 35656222554887711
print(z)         # Output: -3255522

print(type(x))   # <class 'int'>
print(type(y))   # <class 'int'>
print(type(z))   # <class 'int'>
```

### Integer Characteristics
- **No decimal point**
- Can be **positive or negative**
- **Unlimited length** (as large as memory allows)
- Used for counting, indexing, calculations

### More Integer Examples
```python
age = 25
temperature = -10
population = 8000000000
year = 2026
```

---

## Float (float)

**Float** (floating point number) is a number, positive or negative, **containing decimals**.

### Float Examples
```python
x = 1.10
y = 1.0
z = -35.59

print(x)         # Output: 1.1
print(y)         # Output: 1.0
print(z)         # Output: -35.59

print(type(x))   # <class 'float'>
print(type(y))   # <class 'float'>
print(type(z))   # <class 'float'>
```

### Scientific Notation
Float can also be **scientific numbers** with an `e` to indicate the **power of 10**:

```python
x = 35e3        # 35 * 10^3 = 35000
y = 12E4        # 12 * 10^4 = 120000
z = -87.7e100   # -87.7 * 10^100

print(x)         # Output: 35000.0
print(y)         # Output: 120000.0
print(z)         # Output: -8.77e+101

print(type(x))   # <class 'float'>
print(type(y))   # <class 'float'>
print(type(z))   # <class 'float'>
```

### Float Characteristics
- **Has decimal point**
- Can be **positive or negative**
- Can use **scientific notation**
- Used for precise measurements, calculations

### More Float Examples
```python
price = 19.99
pi = 3.14159
temperature = -5.5
weight = 68.5
```

---

## Complex (complex)

**Complex numbers** are written with a `j` as the **imaginary part**:

### Complex Examples
```python
x = 3+5j
y = 5j
z = -5j

print(x)         # Output: (3+5j)
print(y)         # Output: 5j
print(z)         # Output: (-5j)

print(type(x))   # <class 'complex'>
print(type(y))   # <class 'complex'>
print(type(z))   # <class 'complex'>
```

### Complex Number Parts
```python
x = 3+5j
print(x.real)    # Output: 3.0 (real part)
print(x.imag)    # Output: 5.0 (imaginary part)
```

---

## Type Conversion

You can **convert from one type to another** using `int()`, `float()`, and `complex()`:

### Conversion Examples
```python
x = 1      # int
y = 2.8    # float
z = 1j     # complex

# Convert from int to float
a = float(x)
print(a)         # Output: 1.0
print(type(a))   # <class 'float'>

# Convert from float to int
b = int(y)
print(b)         # Output: 2 (decimal removed)
print(type(b))   # <class 'int'>

# Convert from int to complex
c = complex(x)
print(c)         # Output: (1+0j)
print(type(c))   # <class 'complex'>
```

### Conversion Table

| From | To | Function | Example | Result |
|------|-----|----------|---------|--------|
| int | float | `float()` | `float(5)` | `5.0` |
| int | complex | `complex()` | `complex(5)` | `(5+0j)` |
| float | int | `int()` | `int(5.9)` | `5` |
| float | complex | `complex()` | `complex(5.5)` | `(5.5+0j)` |

### Important Note
**You cannot convert complex numbers into another number type.**

```python
z = 1j
# int(z)    # This will cause an error!
# float(z)  # This will also cause an error!
```

---

## Random Numbers

Python does **not have a built-in `random()` function**, but has a **`random` module** for generating random numbers.

### Import Random Module
```python
import random

# Generate random number from 1 to 9
print(random.randrange(1, 10))
```

### Random Number Examples

#### Random Integer in Range
```python
import random

# Random number between 1 and 100
number = random.randint(1, 100)
print(number)

# Random number from 0 to 9
number = random.randrange(10)
print(number)
```

#### Random Float
```python
import random

# Random float between 0 and 1
number = random.random()
print(number)  # Example: 0.7234567

# Random float between 1 and 10
number = random.uniform(1, 10)
print(number)  # Example: 5.678912
```

#### Random Choice from List
```python
import random

colors = ["red", "blue", "green", "yellow"]
choice = random.choice(colors)
print(choice)  # Example: blue
```

---

## Number Operations

### Basic Math Operations
```python
a = 10
b = 3

print(a + b)    # Addition: 13
print(a - b)    # Subtraction: 7
print(a * b)    # Multiplication: 30
print(a / b)    # Division: 3.333...
print(a // b)   # Floor Division: 3
print(a % b)    # Modulus (remainder): 1
print(a ** b)   # Exponentiation: 1000
```

### Mixed Type Operations
```python
x = 5      # int
y = 2.5    # float

result = x + y
print(result)       # Output: 7.5
print(type(result)) # <class 'float'>
```

**Note:** When you mix int and float, the result is always **float**.

---

## Practical Examples

### Example 1: Temperature Converter
```python
celsius = 25
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius}°C = {fahrenheit}°F")
# Output: 25°C = 77.0°F
```

### Example 2: Circle Calculations
```python
import math

radius = 5
area = math.pi * radius ** 2
circumference = 2 * math.pi * radius

print(f"Radius: {radius}")
print(f"Area: {area:.2f}")
print(f"Circumference: {circumference:.2f}")
```

### Example 3: Random Dice Roll
```python
import random

dice1 = random.randint(1, 6)
dice2 = random.randint(1, 6)
total = dice1 + dice2

print(f"Dice 1: {dice1}")
print(f"Dice 2: {dice2}")
print(f"Total: {total}")
```

### Example 4: Price Calculator
```python
price = 19.99
quantity = 3
tax_rate = 0.08

subtotal = price * quantity
tax = subtotal * tax_rate
total = subtotal + tax

print(f"Subtotal: ${subtotal:.2f}")
print(f"Tax: ${tax:.2f}")
print(f"Total: ${total:.2f}")
```

---

## Common Number Methods

### Rounding
```python
x = 3.14159

print(round(x))      # Output: 3
print(round(x, 2))   # Output: 3.14
print(round(x, 3))   # Output: 3.142
```

### Absolute Value
```python
x = -10
print(abs(x))        # Output: 10
```

### Power
```python
print(pow(2, 3))     # Output: 8 (2^3)
print(pow(5, 2))     # Output: 25 (5^2)
```

### Min and Max
```python
print(min(5, 10, 3, 8))   # Output: 3
print(max(5, 10, 3, 8))   # Output: 10
```

---

## Key Takeaways

### ✅ Remember
- **Three numeric types**: int, float, complex
- **int**: Whole numbers, no decimals
- **float**: Numbers with decimals
- **complex**: Numbers with imaginary part (j)
- Use `type()` to check number type
- Use conversion functions to change types

### 🎯 Common Uses
- **int**: Counting, indexing, whole quantities
- **float**: Measurements, prices, scientific calculations
- **complex**: Advanced mathematics, engineering
- **random**: Games, simulations, testing

### ⚠️ Important Notes
- Cannot convert complex to int or float
- Mixing int and float gives float result
- Use `random` module for random numbers
- Float division always returns float

---

**Numbers are fundamental to programming - master them for calculations, data analysis, and problem-solving!**