# Python User Input

## What is User Input?

**Definition:** User input allows programs to interact with users by accepting data during execution.

**Function:** `input()` - pauses program execution and waits for user input.

---

## Basic User Input

### Simple Input
```python
print("Enter your name:")
name = input()
print(f"Hello {name}")
```

**Flow:**
1. Program displays message
2. Waits for user to type and press Enter
3. Stores input in variable
4. Continues execution

---

## Using Prompt

**Better approach:** Use prompt parameter to display message on same line.

```python
name = input("Enter your name: ")
print(f"Hello {name}")
```

**Benefits:**
- Cleaner interface
- Single line for prompt and input
- More user-friendly

---

## Multiple Inputs

```python
name = input("Enter your name: ")
age = input("Enter your age: ")
city = input("Enter your city: ")

print(f"Hello {name}, you are {age} years old and live in {city}")
```

**Note:** Program stops at each `input()` and waits for user response.

---

## Input Data Type

**Important:** `input()` always returns a **string**, even if user enters numbers.

```python
x = input("Enter a number: ")
print(type(x))  # <class 'str'>
print(x)        # "123" (string, not number)
```

---

## Converting Input to Numbers

### Convert to Integer
```python
age = input("Enter your age: ")
age = int(age)  # Convert string to integer
print(f"Next year you will be {age + 1}")
```

### Convert to Float
```python
price = input("Enter price: ")
price = float(price)  # Convert string to float
tax = price * 0.1
print(f"Tax: ${tax:.2f}")
```

### One-Line Conversion
```python
age = int(input("Enter your age: "))
price = float(input("Enter price: "))
```

---

## Input Validation

**Problem:** Program crashes if user enters invalid data.

### Basic Validation with Try-Except
```python
try:
    age = int(input("Enter your age: "))
    print(f"You are {age} years old")
except ValueError:
    print("Please enter a valid number")
```

### Loop Until Valid Input
```python
while True:
    try:
        age = int(input("Enter your age: "))
        break  # Exit loop if conversion successful
    except ValueError:
        print("Please enter a valid number")

print(f"You are {age} years old")
```

---

## Practical Input Validation Functions

### Get Valid Integer
```python
def get_integer(prompt):
    while True:
        try:
            return int(input(prompt))
        except ValueError:
            print("Please enter a valid integer")

age = get_integer("Enter your age: ")
```

### Get Valid Float
```python
def get_float(prompt):
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("Please enter a valid number")

price = get_float("Enter price: ")
```

### Get Valid Choice
```python
def get_choice(prompt, valid_choices):
    while True:
        choice = input(prompt).lower()
        if choice in valid_choices:
            return choice
        print(f"Please choose from: {', '.join(valid_choices)}")

answer = get_choice("Do you agree? (yes/no): ", ["yes", "no"])
```

---

## Common Input Patterns

### Yes/No Questions
```python
answer = input("Do you want to continue? (y/n): ").lower()
if answer in ['y', 'yes']:
    print("Continuing...")
else:
    print("Stopping...")
```

### Menu Selection
```python
print("1. Add item")
print("2. Remove item")
print("3. View items")
choice = input("Select option (1-3): ")

if choice == "1":
    print("Adding item...")
elif choice == "2":
    print("Removing item...")
elif choice == "3":
    print("Viewing items...")
else:
    print("Invalid choice")
```

### Multiple Values in One Input
```python
# Space-separated values
numbers = input("Enter numbers separated by spaces: ").split()
numbers = [int(x) for x in numbers]
print(f"Sum: {sum(numbers)}")

# Comma-separated values
items = input("Enter items separated by commas: ").split(',')
items = [item.strip() for item in items]  # Remove extra spaces
print(f"Items: {items}")
```

---

## Advanced Input Examples

### Calculator
```python
def calculator():
    while True:
        try:
            num1 = float(input("Enter first number: "))
            operator = input("Enter operator (+, -, *, /): ")
            num2 = float(input("Enter second number: "))
            
            if operator == '+':
                result = num1 + num2
            elif operator == '-':
                result = num1 - num2
            elif operator == '*':
                result = num1 * num2
            elif operator == '/':
                if num2 == 0:
                    print("Cannot divide by zero!")
                    continue
                result = num1 / num2
            else:
                print("Invalid operator!")
                continue
            
            print(f"Result: {result}")
            break
            
        except ValueError:
            print("Please enter valid numbers!")

calculator()
```

### User Registration
```python
def register_user():
    print("User Registration")
    print("-" * 20)
    
    name = input("Full name: ").strip()
    while not name:
        name = input("Name cannot be empty. Full name: ").strip()
    
    email = input("Email: ").strip()
    while '@' not in email:
        email = input("Please enter valid email: ").strip()
    
    age = get_integer("Age: ")
    while age < 0 or age > 120:
        age = get_integer("Please enter valid age (0-120): ")
    
    print(f"\nRegistration successful!")
    print(f"Name: {name}")
    print(f"Email: {email}")
    print(f"Age: {age}")

def get_integer(prompt):
    while True:
        try:
            return int(input(prompt))
        except ValueError:
            print("Please enter a valid number")

register_user()
```

---

## Input Security Considerations

### Avoid eval() with User Input
```python
# Dangerous - never do this
user_code = input("Enter Python code: ")
eval(user_code)  # Security risk!

# Safe alternative - validate specific inputs
```

### Sanitize Input
```python
def sanitize_input(text):
    # Remove leading/trailing whitespace
    text = text.strip()
    # Remove special characters if needed
    # Add other sanitization as required
    return text

name = sanitize_input(input("Enter your name: "))
```

---

## Input with Default Values

```python
def get_input_with_default(prompt, default):
    user_input = input(f"{prompt} (default: {default}): ").strip()
    return user_input if user_input else default

name = get_input_with_default("Enter your name", "Guest")
age = int(get_input_with_default("Enter your age", "18"))
```

---

## Quick Reference

### Basic Input
```python
name = input("Enter name: ")          # String input
age = int(input("Enter age: "))       # Integer input
price = float(input("Enter price: ")) # Float input
```

### Input Validation
```python
# Simple validation
try:
    number = int(input("Enter number: "))
except ValueError:
    print("Invalid input")

# Loop until valid
while True:
    try:
        number = int(input("Enter number: "))
        break
    except ValueError:
        print("Please enter a valid number")
```

### Common Patterns
```python
# Yes/No
answer = input("Continue? (y/n): ").lower()

# Multiple values
numbers = input("Enter numbers: ").split()

# Menu choice
choice = input("Select (1-3): ")
```

---

## Key Takeaways

### ✅ Remember
- **input()** always returns a string
- **Convert** to int/float when needed
- **Validate** user input to prevent crashes
- **Use prompts** for better user experience
- **Handle errors** with try-except
- **Loop** until valid input received
- **Sanitize** input for security
- **Provide defaults** when appropriate

### 🎯 Interview Important
- input() returns string data type
- How to convert string input to numbers
- Input validation techniques
- Error handling with user input
- Security considerations with user input
- Common input patterns (yes/no, menus)
- Difference between input() and raw_input() (Python 2)

---

**Use input() to create interactive programs that respond to user needs!**