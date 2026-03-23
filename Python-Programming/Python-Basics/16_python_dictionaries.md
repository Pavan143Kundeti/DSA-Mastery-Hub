# Python Dictionaries

## What are Dictionaries?

**Definition:** Dictionaries store data values in key:value pairs. Dictionaries are ordered* (Python 3.7+), changeable, and do not allow duplicate keys.

*Ordered since Python 3.7. In Python 3.6 and earlier, dictionaries were unordered.

```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
print(thisdict)  # {'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
```

---

## Dictionary Characteristics

| Property | Description | Example |
|----------|-------------|---------|
| **Ordered** | Items have defined order (Python 3.7+) | Order maintained |
| **Changeable** | Can change, add, remove items | Mutable |
| **No Duplicate Keys** | Keys must be unique | Duplicate keys overwrite |
| **Key:Value Pairs** | Data stored as pairs | `"brand": "Ford"` |

---

## Creating Dictionaries

### Using Curly Brackets
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
print(thisdict)
```

### Using dict() Constructor
```python
thisdict = dict(name="John", age=36, country="Norway")
print(thisdict)  # {'name': 'John', 'age': 36, 'country': 'Norway'}
```

### Different Data Types
```python
thisdict = {
    "brand": "Ford",
    "electric": False,
    "year": 1964,
    "colors": ["red", "white", "blue"]
}
```

---

## Dictionary Properties

### No Duplicate Keys
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964,
    "year": 2020  # This will overwrite the previous "year"
}
print(thisdict)  # {'brand': 'Ford', 'model': 'Mustang', 'year': 2020}
```

### Dictionary Length
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
print(len(thisdict))  # Output: 3
```

### Dictionary Type
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
print(type(thisdict))  # Output: <class 'dict'>
```

---

## Collections Comparison

| Collection | Ordered | Changeable | Duplicates | Access By | Syntax |
|------------|---------|------------|------------|-----------|--------|
| **List** | ✅ Yes | ✅ Yes | ✅ Yes | Index | `[]` |
| **Tuple** | ✅ Yes | ❌ No | ✅ Yes | Index | `()` |
| **Set** | ❌ No | ✅ Yes* | ❌ No | - | `{}` |
| **Dictionary** | ✅ Yes** | ✅ Yes | ❌ No | Key | `{"key": "value"}` |

*Can add/remove, not change  
**Ordered since Python 3.7

---

## Access Dictionary Items

### Access by Key Name
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

# Using square brackets
x = thisdict["model"]
print(x)  # Mustang

# Using get() method
x = thisdict.get("model")
print(x)  # Mustang
```

### Get Keys
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

x = thisdict.keys()
print(x)  # dict_keys(['brand', 'model', 'year'])
```

### Get Values
```python
x = thisdict.values()
print(x)  # dict_values(['Ford', 'Mustang', 1964])
```

### Get Items (Key:Value Pairs)
```python
x = thisdict.items()
print(x)  # dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)])
```

### Dynamic Views
```python
car = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

x = car.keys()
print(x)  # Before: dict_keys(['brand', 'model', 'year'])

car["color"] = "white"
print(x)  # After: dict_keys(['brand', 'model', 'year', 'color'])
```

### Check if Key Exists
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

if "model" in thisdict:
    print("Yes, 'model' is a key")
```

---

## Change Dictionary Items

### Change Value
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

thisdict["year"] = 2018
print(thisdict)  # {'brand': 'Ford', 'model': 'Mustang', 'year': 2018}
```

### Update Dictionary
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

thisdict.update({"year": 2020})
print(thisdict)  # {'brand': 'Ford', 'model': 'Mustang', 'year': 2020}
```

---

## Add Dictionary Items

### Add New Item
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

thisdict["color"] = "red"
print(thisdict)  # {'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red'}
```

### Using update()
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

thisdict.update({"color": "red"})
print(thisdict)  # {'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red'}
```

---

## Remove Dictionary Items

| Method | Description | Returns | Error if Not Found |
|--------|-------------|---------|-------------------|
| `pop(key)` | Removes specified key | Value of removed item | ✅ Yes |
| `popitem()` | Removes last inserted item | Tuple (key, value) | ✅ Yes (if empty) |
| `del dict[key]` | Deletes specified key | Nothing | ✅ Yes |
| `del dict` | Deletes entire dictionary | Nothing | N/A |
| `clear()` | Empties dictionary | Nothing | ❌ No |

### Examples
```python
# pop() - removes specified key
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
thisdict.pop("model")
print(thisdict)  # {'brand': 'Ford', 'year': 1964}

# popitem() - removes last item
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
thisdict.popitem()
print(thisdict)  # {'brand': 'Ford', 'model': 'Mustang'}

# del - removes specified key
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
del thisdict["model"]
print(thisdict)  # {'brand': 'Ford', 'year': 1964}

# clear() - empties dictionary
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
thisdict.clear()
print(thisdict)  # {}
```

---

## Loop Through Dictionaries

### Loop Through Keys
```python
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

# Default - returns keys
for x in thisdict:
    print(x)  # brand, model, year

# Using keys() method
for x in thisdict.keys():
    print(x)  # brand, model, year
```

### Loop Through Values
```python
# Access values using keys
for x in thisdict:
    print(thisdict[x])  # Ford, Mustang, 1964

# Using values() method
for x in thisdict.values():
    print(x)  # Ford, Mustang, 1964
```

### Loop Through Key:Value Pairs
```python
for x, y in thisdict.items():
    print(x, y)
# Output:
# brand Ford
# model Mustang
# year 1964
```

---

## Copy Dictionaries

**Important:** `dict2 = dict1` creates a reference, not a copy!

| Method | Syntax | Description |
|--------|--------|-------------|
| `copy()` | `dict2 = dict1.copy()` | Creates a copy |
| `dict()` | `dict2 = dict(dict1)` | Creates a copy |

### Examples
```python
# Using copy()
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
mydict = thisdict.copy()
print(mydict)

# Using dict()
thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
mydict = dict(thisdict)
print(mydict)
```

---

## Nested Dictionaries

**Definition:** A dictionary containing other dictionaries.

### Create Nested Dictionary
```python
myfamily = {
    "child1": {
        "name": "Emil",
        "year": 2004
    },
    "child2": {
        "name": "Tobias",
        "year": 2007
    },
    "child3": {
        "name": "Linus",
        "year": 2011
    }
}
```

### Add Existing Dictionaries
```python
child1 = {
    "name": "Emil",
    "year": 2004
}
child2 = {
    "name": "Tobias",
    "year": 2007
}
child3 = {
    "name": "Linus",
    "year": 2011
}

myfamily = {
    "child1": child1,
    "child2": child2,
    "child3": child3
}
```

### Access Nested Items
```python
print(myfamily["child2"]["name"])  # Output: Tobias
```

### Loop Through Nested Dictionaries
```python
for x, obj in myfamily.items():
    print(x)
    for y in obj:
        print(y + ':', obj[y])

# Output:
# child1
# name: Emil
# year: 2004
# child2
# name: Tobias
# year: 2007
# child3
# name: Linus
# year: 2011
```

---

## Dictionary Methods Reference

| Method | Description | Example |
|--------|-------------|---------|
| `clear()` | Removes all elements | `dict.clear()` |
| `copy()` | Returns a copy | `newdict = dict.copy()` |
| `fromkeys()` | Returns dict with specified keys | `dict.fromkeys(keys, value)` |
| `get()` | Returns value of specified key | `dict.get("key")` |
| `items()` | Returns list of key:value tuples | `dict.items()` |
| `keys()` | Returns list of keys | `dict.keys()` |
| `pop()` | Removes specified key | `dict.pop("key")` |
| `popitem()` | Removes last inserted item | `dict.popitem()` |
| `setdefault()` | Returns value or sets default | `dict.setdefault("key", "default")` |
| `update()` | Updates dictionary | `dict.update({"key": "value"})` |
| `values()` | Returns list of values | `dict.values()` |

---

## Practical Examples

### Example 1: Student Information
```python
student = {
    "name": "Alice",
    "age": 20,
    "major": "Computer Science",
    "gpa": 3.8,
    "courses": ["Math", "Physics", "Programming"]
}

print(f"Name: {student['name']}")
print(f"GPA: {student['gpa']}")
print(f"Courses: {', '.join(student['courses'])}")
```

### Example 2: Word Counter
```python
text = "hello world hello python world"
words = text.split()

word_count = {}
for word in words:
    if word in word_count:
        word_count[word] += 1
    else:
        word_count[word] = 1

print(word_count)  # {'hello': 2, 'world': 2, 'python': 1}
```

### Example 3: Phone Book
```python
phonebook = {
    "Alice": "555-1234",
    "Bob": "555-5678",
    "Charlie": "555-9012"
}

# Add new contact
phonebook["David"] = "555-3456"

# Update contact
phonebook["Alice"] = "555-0000"

# Remove contact
phonebook.pop("Bob")

print(phonebook)
```

### Example 4: Configuration Settings
```python
config = {
    "database": {
        "host": "localhost",
        "port": 5432,
        "username": "admin"
    },
    "app": {
        "debug": True,
        "version": "1.0.0"
    }
}

print(config["database"]["host"])  # localhost
print(config["app"]["debug"])      # True
```

---

## Key Takeaways

### ✅ Remember
- Dictionaries use **curly brackets** `{}`
- Store data as **key:value pairs**
- **Ordered** (Python 3.7+), **changeable**, **no duplicate keys**
- Access items by **key name**, not index
- Keys must be **unique and immutable** (strings, numbers, tuples)
- Values can be **any data type**

### 🎯 Common Operations
- **Access**: `dict[key]`, `dict.get(key)`
- **Add**: `dict[key] = value`, `dict.update()`
- **Remove**: `pop()`, `popitem()`, `del`, `clear()`
- **Loop**: `keys()`, `values()`, `items()`
- **Copy**: `copy()`, `dict()`

### 🔧 When to Use Dictionaries
- **Store related data** with descriptive keys
- **Fast lookups** by key name
- **Configuration settings**
- **Counting occurrences** (word frequency)
- **Mapping relationships** (name to phone number)
- **JSON-like data structures**

---

**Dictionaries are perfect for storing and accessing data with meaningful keys!**