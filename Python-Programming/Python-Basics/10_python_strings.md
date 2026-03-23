# Python Strings

## Creating Strings

Strings are surrounded by **single** or **double** quotes:

```python
print("Hello")  # Double quotes
print('Hello')  # Single quotes - same result
```

### Quotes Inside Strings
Use different quotes inside strings:

```python
print("It's alright")
print("He is called 'Johnny'")
print('He is called "Johnny"')
```

### Assign String to Variable
```python
a = "Hello"
print(a)  # Output: Hello
```

---

## Multiline Strings

Use **three quotes** for multiline strings:

```python
# Three double quotes
a = """Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor."""
print(a)

# Three single quotes
a = '''Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor.'''
print(a)
```

---

## String Slicing

Get a range of characters using **slice syntax**:

```python
b = "Hello, World!"
print(b[2:5])    # Output: llo (position 2 to 5, not including 5)
print(b[:5])     # Output: Hello (start to position 5)
print(b[7:])     # Output: World! (position 7 to end)
print(b[-5:-2])  # Output: orl (negative indexing)
```

**Note:** First character has index 0.

---

## String Methods

### Upper and Lower Case
```python
a = "Hello, World!"
print(a.upper())  # Output: HELLO, WORLD!
print(a.lower())  # Output: hello, world!
```

### Remove Whitespace
```python
a = "  Hello, World!  "
print(a.strip())  # Output: "Hello, World!"
```

### Replace String
```python
a = "Hello, World!"
print(a.replace("H", "J"))  # Output: Jello, World!
```

### Split String
```python
a = "Hello, World!"
print(a.split(","))  # Output: ['Hello', ' World!']
```

---

## String Concatenation

Combine strings using the **+** operator:

```python
a = "Hello"
b = "World"
c = a + b
print(c)  # Output: HelloWorld

# Add space
c = a + " " + b
print(c)  # Output: Hello World
```

---

## String Formatting

### F-Strings (Recommended)
Put **f** before the string and use **{}** for variables:

```python
age = 36
txt = f"My name is John, I am {age}"
print(txt)  # Output: My name is John, I am 36

# With formatting
price = 59
txt = f"The price is {price:.2f} dollars"
print(txt)  # Output: The price is 59.00 dollars

# With operations
txt = f"The price is {20 * 59} dollars"
print(txt)  # Output: The price is 1180 dollars
```

---

## Escape Characters

Use **backslash \\** to insert special characters:

```python
txt = "We are the so-called \"Vikings\" from the north."
print(txt)  # Output: We are the so-called "Vikings" from the north.
```

### Common Escape Characters

| Code | Result |
|------|--------|
| `\'` | Single Quote |
| `\\` | Backslash |
| `\n` | New Line |
| `\t` | Tab |

```python
print("Hello\nWorld")   # New line
print("Hello\tWorld")   # Tab
print("This is a backslash: \\")
```

---

## Essential String Methods

### Check Content
```python
txt = "Hello World"
print(txt.startswith("Hello"))  # True
print(txt.endswith("World"))    # True
print(txt.find("World"))        # 6 (position)
print(txt.count("l"))           # 3 (occurrences)
```

### Case Checking
```python
txt = "hello"
print(txt.islower())   # True
print(txt.isupper())   # False
print(txt.isalpha())   # True (all letters)
print(txt.isdigit())   # False (not all digits)
```

### Modify Strings
```python
txt = "hello world"
print(txt.capitalize())  # Hello world
print(txt.title())       # Hello World
print(txt.swapcase())    # HELLO WORLD
```

### Join and Split
```python
# Join list into string
words = ["Hello", "World"]
result = " ".join(words)
print(result)  # Output: Hello World

# Split string into list
txt = "apple,banana,cherry"
fruits = txt.split(",")
print(fruits)  # Output: ['apple', 'banana', 'cherry']
```

---

## Common String Methods Reference

| Method | Description | Example |
|--------|-------------|---------|
| `upper()` | Convert to uppercase | `"hello".upper()` → `"HELLO"` |
| `lower()` | Convert to lowercase | `"HELLO".lower()` → `"hello"` |
| `strip()` | Remove whitespace | `" hi ".strip()` → `"hi"` |
| `replace(old, new)` | Replace text | `"hi".replace("h", "b")` → `"bi"` |
| `split(sep)` | Split into list | `"a,b".split(",")` → `['a', 'b']` |
| `find(text)` | Find position | `"hello".find("e")` → `1` |
| `count(text)` | Count occurrences | `"hello".count("l")` → `2` |
| `startswith(text)` | Check start | `"hello".startswith("he")` → `True` |
| `endswith(text)` | Check end | `"hello".endswith("lo")` → `True` |
| `isdigit()` | Check if digits | `"123".isdigit()` → `True` |
| `isalpha()` | Check if letters | `"abc".isalpha()` → `True` |
| `capitalize()` | First letter upper | `"hello".capitalize()` → `"Hello"` |
| `title()` | Title case | `"hello world".title()` → `"Hello World"` |
| `join(list)` | Join list items | `"-".join(['a','b'])` → `"a-b"` |

---

## Practical Examples

### Example 1: User Greeting
```python
name = input("Enter your name: ")
age = input("Enter your age: ")
print(f"Hello {name.title()}, you are {age} years old!")
```

### Example 2: Email Validation
```python
email = "user@example.com"
if "@" in email and email.endswith(".com"):
    print("Valid email")
else:
    print("Invalid email")
```

### Example 3: Clean User Input
```python
user_input = "  HELLO WORLD  "
cleaned = user_input.strip().lower()
print(cleaned)  # Output: hello world
```

### Example 4: Word Counter
```python
sentence = "Python is awesome and Python is easy"
words = sentence.split()
print(f"Total words: {len(words)}")
print(f"'Python' appears {sentence.count('Python')} times")
```

---

## String Indexing

Access individual characters:

```python
txt = "Hello"
print(txt[0])   # H (first character)
print(txt[1])   # e
print(txt[-1])  # o (last character)
print(txt[-2])  # l (second from end)
```

---

## String Length

Use `len()` to get string length:

```python
txt = "Hello World"
print(len(txt))  # Output: 11
```

---

## Check Substring

Use `in` keyword:

```python
txt = "Hello World"
print("World" in txt)      # True
print("world" in txt)      # False (case-sensitive)
print("Python" not in txt) # True
```

---

## Key Takeaways

### ✅ Remember
- Strings use **single** or **double** quotes
- Use **f-strings** for formatting (modern way)
- Strings are **immutable** (can't change original)
- **Index starts at 0**
- Use **escape characters** for special characters

### 🎯 Most Used Methods
- `upper()`, `lower()` - Change case
- `strip()` - Remove whitespace
- `split()` - Convert to list
- `replace()` - Replace text
- `find()` - Find position
- `format()` or f-strings - Insert variables

### ⚠️ Common Mistakes
- Forgetting quotes around strings
- Mixing quote types incorrectly
- Not using escape characters
- Trying to modify strings directly (they're immutable)

---

**Strings are one of the most used data types in Python - master them for text processing!**