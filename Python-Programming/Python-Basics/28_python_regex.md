# Python RegEx

## What is RegEx?

**Definition:** RegEx (Regular Expression) is a sequence of characters that forms a search pattern.

**Use:** Check if a string contains a specified search pattern.

---

## RegEx Module

Python has a built-in `re` module for regular expressions.

```python
import re
```

### Basic Example
```python
import re

txt = "The rain in Spain"
x = re.search("^The.*Spain$", txt)

if x:
    print("Match found!")
else:
    print("No match")
```

---

## RegEx Functions

| Function | Description | Returns |
|----------|-------------|---------|
| `findall()` | Find all matches | List of matches |
| `search()` | Find first match | Match object or None |
| `split()` | Split string at matches | List of strings |
| `sub()` | Replace matches | Modified string |

---

## findall() Function

Returns a list of all matches.

```python
import re

txt = "The rain in Spain"
x = re.findall("ai", txt)
print(x)  # Output: ['ai', 'ai']
```

### No Matches
```python
x = re.findall("Portugal", txt)
print(x)  # Output: []
```

---

## search() Function

Returns Match object for first match, or None.

```python
import re

txt = "The rain in Spain"
x = re.search("\s", txt)  # Find first whitespace

if x:
    print("First whitespace at position:", x.start())
else:
    print("No match found")
```

---

## split() Function

Split string at each match.

```python
import re

txt = "The rain in Spain"
x = re.split("\s", txt)
print(x)  # Output: ['The', 'rain', 'in', 'Spain']
```

### Limit Splits
```python
x = re.split("\s", txt, 1)  # Split only at first match
print(x)  # Output: ['The', 'rain in Spain']
```

---

## sub() Function

Replace matches with specified text.

```python
import re

txt = "The rain in Spain"
x = re.sub("\s", "9", txt)
print(x)  # Output: The9rain9in9Spain
```

### Limit Replacements
```python
x = re.sub("\s", "9", txt, 2)  # Replace first 2 matches
print(x)  # Output: The9rain9in Spain
```

---

## Metacharacters

| Character | Description | Example |
|-----------|-------------|---------|
| `[]` | Set of characters | `[a-m]` |
| `\` | Special sequence | `\d` |
| `.` | Any character | `he..o` |
| `^` | Starts with | `^hello` |
| `$` | Ends with | `world$` |
| `*` | Zero or more | `he.*o` |
| `+` | One or more | `he.+o` |
| `?` | Zero or one | `he.?o` |
| `{}` | Exact number | `he.{2}o` |
| `\|` | Either or | `cat\|dog` |

---

## Special Sequences

| Sequence | Description | Example |
|----------|-------------|---------|
| `\A` | Start of string | `\AThe` |
| `\b` | Word boundary | `r"\bain"` |
| `\B` | Not word boundary | `r"\Bain"` |
| `\d` | Digit (0-9) | `\d` |
| `\D` | Not digit | `\D` |
| `\s` | Whitespace | `\s` |
| `\S` | Not whitespace | `\S` |
| `\w` | Word character | `\w` |
| `\W` | Not word character | `\W` |
| `\Z` | End of string | `Spain\Z` |

---

## Sets (Character Classes)

| Set | Description |
|-----|-------------|
| `[arn]` | Any of a, r, or n |
| `[a-n]` | Any lowercase a to n |
| `[^arn]` | Any except a, r, n |
| `[0-9]` | Any digit 0 to 9 |
| `[0-5][0-9]` | Numbers 00 to 59 |
| `[a-zA-Z]` | Any letter |

---

## Practical Examples

### Find Email Pattern
```python
import re

text = "Contact us at info@example.com or support@test.org"
emails = re.findall(r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b', text)
print(emails)  # ['info@example.com', 'support@test.org']
```

### Validate Phone Number
```python
import re

phone = "123-456-7890"
pattern = r'^\d{3}-\d{3}-\d{4}$'

if re.match(pattern, phone):
    print("Valid phone number")
else:
    print("Invalid phone number")
```

### Extract Numbers
```python
import re

text = "I have 5 apples and 10 oranges"
numbers = re.findall(r'\d+', text)
print(numbers)  # ['5', '10']
```

### Clean Text
```python
import re

text = "Hello!!!   World???"
clean_text = re.sub(r'[!?]+', '', text)  # Remove ! and ?
clean_text = re.sub(r'\s+', ' ', clean_text)  # Replace multiple spaces
print(clean_text.strip())  # "Hello World"
```

---

## Match Object

When `search()` finds a match, it returns a Match object.

```python
import re

txt = "The rain in Spain"
x = re.search(r"\bS\w+", txt)

if x:
    print(x.span())    # (13, 18) - start and end position
    print(x.string)   # "The rain in Spain" - original string
    print(x.group())  # "Spain" - matched text
```

### Match Object Methods

| Method | Description |
|--------|-------------|
| `.span()` | Start and end positions |
| `.string` | Original string |
| `.group()` | Matched text |
| `.start()` | Start position |
| `.end()` | End position |

---

## Flags

| Flag | Description |
|------|-------------|
| `re.IGNORECASE` or `re.I` | Case-insensitive |
| `re.MULTILINE` or `re.M` | Multiline mode |
| `re.DOTALL` or `re.S` | Dot matches newline |

### Example with Flags
```python
import re

text = "Hello WORLD"
result = re.findall("hello", text, re.IGNORECASE)
print(result)  # ['Hello']
```

---

## Common Patterns

| Pattern | Description | Example |
|---------|-------------|---------|
| `^\d+$` | Only digits | "123" ✓ |
| `^[a-zA-Z]+$` | Only letters | "Hello" ✓ |
| `^\w+@\w+\.\w+$` | Simple email | "user@domain.com" ✓ |
| `^\d{3}-\d{3}-\d{4}$` | Phone format | "123-456-7890" ✓ |

---

## Quick Reference

### Basic Usage
```python
import re

# Find all matches
re.findall(pattern, string)

# Find first match
re.search(pattern, string)

# Split string
re.split(pattern, string)

# Replace matches
re.sub(pattern, replacement, string)
```

### Common Patterns
```python
# Digits: \d or [0-9]
# Letters: [a-zA-Z]
# Word characters: \w
# Whitespace: \s
# Start of string: ^
# End of string: $
```

---

## Key Takeaways

### ✅ Remember
- **RegEx** finds patterns in strings
- **re module** provides RegEx functions
- **findall()** returns list of all matches
- **search()** returns first match object
- **split()** splits string at matches
- **sub()** replaces matches
- **Metacharacters** have special meanings
- **Sets []** match character ranges
- **Match object** has span(), group(), string methods

### 🎯 Interview Important
- Common RegEx patterns (email, phone, etc.)
- Difference between findall() and search()
- Metacharacters and their meanings
- Match object methods
- When to use raw strings (r"")
- RegEx flags for case-insensitive matching

---

**Use RegEx for powerful pattern matching and text processing!**