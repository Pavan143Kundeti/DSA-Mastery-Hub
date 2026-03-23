# Python JSON

## What is JSON?

**Definition:** JSON (JavaScript Object Notation) is a syntax for storing and exchanging data.

**Format:** Text written with JavaScript object notation.

---

## JSON in Python

Python has a built-in `json` module to work with JSON data.

```python
import json
```

---

## Parse JSON - Convert JSON to Python

Use `json.loads()` to convert JSON string to Python dictionary.

```python
import json

# JSON string
x = '{ "name":"John", "age":30, "city":"New York"}'

# Parse JSON
y = json.loads(x)

# Result is Python dictionary
print(y["age"])  # Output: 30
```

**Method:** `json.loads()` (load string)
**Result:** Python dictionary

---

## Convert Python to JSON

Use `json.dumps()` to convert Python object to JSON string.

```python
import json

# Python dictionary
x = {
    "name": "John",
    "age": 30,
    "city": "New York"
}

# Convert to JSON
y = json.dumps(x)

# Result is JSON string
print(y)  # Output: {"name": "John", "age": 30, "city": "New York"}
```

**Method:** `json.dumps()` (dump string)
**Result:** JSON string

---

## Python to JSON Data Types

| Python Type | JSON Type |
|-------------|-----------|
| `dict` | Object |
| `list` | Array |
| `tuple` | Array |
| `str` | String |
| `int` | Number |
| `float` | Number |
| `True` | true |
| `False` | false |
| `None` | null |

---

## Convert Different Python Types

```python
import json

print(json.dumps({"name": "John", "age": 30}))  # Object
print(json.dumps(["apple", "bananas"]))         # Array
print(json.dumps(("apple", "bananas")))         # Array
print(json.dumps("hello"))                      # String
print(json.dumps(42))                           # Number
print(json.dumps(31.76))                        # Number
print(json.dumps(True))                         # true
print(json.dumps(False))                        # false
print(json.dumps(None))                         # null
```

---

## Complex Python Object

```python
import json

x = {
    "name": "John",
    "age": 30,
    "married": True,
    "divorced": False,
    "children": ("Ann", "Billy"),
    "pets": None,
    "cars": [
        {"model": "BMW 230", "mpg": 27.5},
        {"model": "Ford Edge", "mpg": 24.1}
    ]
}

print(json.dumps(x))
```

---

## Format JSON Output

### Basic Output (Hard to Read)
```python
{"name": "John", "age": 30, "married": true, "divorced": false}
```

### With Indentation
```python
json.dumps(x, indent=4)
```

**Output:**
```json
{
    "name": "John",
    "age": 30,
    "married": true,
    "divorced": false
}
```

---

## Custom Separators

Default separators: `(", ", ": ")`

```python
json.dumps(x, indent=4, separators=(". ", " = "))
```

**Output:**
```json
{
    "name" = "John".
    "age" = 30.
    "married" = true.
    "divorced" = false
}
```

---

## Sort Keys

```python
json.dumps(x, indent=4, sort_keys=True)
```

**Output:** Keys sorted alphabetically.

---

## JSON Methods Summary

| Method | Purpose | Input | Output |
|--------|---------|-------|--------|
| `json.loads()` | Parse JSON | JSON string | Python dict |
| `json.dumps()` | Create JSON | Python object | JSON string |

---

## JSON Parameters

### json.dumps() Parameters

| Parameter | Description | Example |
|-----------|-------------|---------|
| `indent` | Number of spaces for indentation | `indent=4` |
| `separators` | Custom separators | `separators=(", ", ": ")` |
| `sort_keys` | Sort keys alphabetically | `sort_keys=True` |

---

## Practical Examples

### Reading JSON from String
```python
import json

json_string = '{"users": [{"name": "Alice", "age": 25}, {"name": "Bob", "age": 30}]}'
data = json.loads(json_string)

for user in data["users"]:
    print(f"{user['name']} is {user['age']} years old")
```

### Creating JSON for API
```python
import json

user_data = {
    "username": "john_doe",
    "email": "john@example.com",
    "preferences": {
        "theme": "dark",
        "notifications": True
    }
}

json_output = json.dumps(user_data, indent=2)
print(json_output)
```

### Working with Lists
```python
import json

# Python list to JSON
fruits = ["apple", "banana", "cherry"]
json_fruits = json.dumps(fruits)
print(json_fruits)  # ["apple", "banana", "cherry"]

# JSON to Python list
json_string = '["red", "green", "blue"]'
colors = json.loads(json_string)
print(colors[0])  # red
```

---

## Common Use Cases

| Use Case | Method | Example |
|----------|--------|---------|
| API responses | `json.loads()` | Parse server response |
| API requests | `json.dumps()` | Send data to server |
| Config files | Both | Read/write settings |
| Data storage | Both | Save/load application data |

---

## Error Handling

```python
import json

try:
    # Invalid JSON
    invalid_json = '{"name": "John", "age":}'
    data = json.loads(invalid_json)
except json.JSONDecodeError as e:
    print(f"JSON Error: {e}")
```

---

## Quick Reference

### Parse JSON
```python
import json
data = json.loads(json_string)
```

### Create JSON
```python
import json
json_string = json.dumps(python_object)
```

### Formatted JSON
```python
json.dumps(data, indent=4, sort_keys=True)
```

---

## Key Takeaways

### ✅ Remember
- **JSON** is text format for data exchange
- **json.loads()** converts JSON string to Python dict
- **json.dumps()** converts Python object to JSON string
- **indent** parameter for readable formatting
- **sort_keys** for alphabetical key ordering
- **Python types** map to specific JSON types
- **Error handling** for invalid JSON

### 🎯 Interview Important
- Difference between loads() and dumps()
- Python to JSON type mapping
- JSON formatting options
- Common JSON use cases (APIs, config files)
- JSON error handling
- When to use JSON vs other formats

---

**Use JSON for data exchange between applications and APIs!**