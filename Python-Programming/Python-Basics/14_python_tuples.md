# Python Tuples

## What are Tuples?

**Definition:** Tuples are used to store multiple items in a single variable. Tuples are ordered and unchangeable (immutable).

```python
mytuple = ("apple", "banana", "cherry")
print(mytuple)  # Output: ('apple', 'banana', 'cherry')
```

---

## Tuple Characteristics

| Property | Description | Example |
|----------|-------------|---------|
| **Ordered** | Items have a defined order | `("a", "b", "c")` stays same |
| **Unchangeable** | Cannot change, add, or remove items | Immutable after creation |
| **Allow Duplicates** | Can have items with same value | `("apple", "apple")` is valid |
| **Indexed** | First item is `[0]`, second is `[1]` | `mytuple[0]` gets first item |

---

## Creating Tuples

### Using Round Brackets
```python
thistuple = ("apple", "banana", "cherry")
print(thistuple)
```

### Using tuple() Constructor
```python
thistuple = tuple(("apple", "banana", "cherry"))  # Note double parentheses
print(thistuple)
```

### One Item Tuple (Important!)
```python
# Correct - with comma
thistuple = ("apple",)
print(type(thistuple))  # <class 'tuple'>

# Wrong - without comma (this is a string!)
thistuple = ("apple")
print(type(thistuple))  # <class 'str'>
```

### Different Data Types
```python
tuple1 = ("apple", "banana", "cherry")       # Strings
tuple2 = (1, 5, 7, 9, 3)                     # Integers
tuple3 = (True, False, False)                # Booleans
tuple4 = ("abc", 34, True, 40, "male")       # Mixed types
```

---

## Tuple Properties

### Tuple Length
```python
thistuple = ("apple", "banana", "cherry")
print(len(thistuple))  # Output: 3
```

### Tuple Type
```python
mytuple = ("apple", "banana", "cherry")
print(type(mytuple))  # Output: <class 'tuple'>
```

### Allow Duplicates
```python
thistuple = ("apple", "banana", "cherry", "apple", "cherry")
print(thistuple)  # Duplicates are allowed
```

---

## Collections Comparison

| Collection | Ordered | Changeable | Duplicates | Syntax |
|------------|---------|------------|------------|--------|
| **List** | ✅ Yes | ✅ Yes | ✅ Yes | `[]` |
| **Tuple** | ✅ Yes | ❌ No | ✅ Yes | `()` |
| **Set** | ❌ No | ✅ Yes* | ❌ No | `{}` |
| **Dictionary** | ✅ Yes** | ✅ Yes | ❌ No | `{"key": "value"}` |

*Set items unchangeable, but can add/remove  
**Ordered since Python 3.7

---

## Access Tuple Items

### By Index
```python
thistuple = ("apple", "banana", "cherry")
print(thistuple[0])   # Output: apple
print(thistuple[1])   # Output: banana
print(thistuple[2])   # Output: cherry
```

### Negative Indexing
```python
thistuple = ("apple", "banana", "cherry")
print(thistuple[-1])  # Output: cherry (last item)
print(thistuple[-2])  # Output: banana (second last)
print(thistuple[-3])  # Output: apple (third last)
```

### Range of Indexes (Slicing)

| Syntax | Description | Example | Result |
|--------|-------------|---------|--------|
| `[start:end]` | From start to end-1 | `[2:5]` | Items 2, 3, 4 |
| `[:end]` | From beginning to end-1 | `[:4]` | Items 0, 1, 2, 3 |
| `[start:]` | From start to end | `[2:]` | Items 2 to last |
| `[-start:-end]` | Negative range | `[-4:-1]` | Last 4 to last 1 |

```python
thistuple = ("apple", "banana", "cherry", "orange", "kiwi", "melon", "mango")

print(thistuple[2:5])    # ('cherry', 'orange', 'kiwi')
print(thistuple[:4])     # ('apple', 'banana', 'cherry', 'orange')
print(thistuple[2:])     # ('cherry', 'orange', 'kiwi', 'melon', 'mango')
print(thistuple[-4:-1])  # ('orange', 'kiwi', 'melon')
```

### Check if Item Exists
```python
thistuple = ("apple", "banana", "cherry")
if "apple" in thistuple:
    print("Yes, 'apple' is in the tuple")
```

---

## Update Tuples (Workarounds)

**Important:** Tuples are unchangeable, but there are workarounds!

### Change Tuple Values
Convert to list, modify, convert back:

```python
x = ("apple", "banana", "cherry")
y = list(x)
y[1] = "kiwi"
x = tuple(y)
print(x)  # ('apple', 'kiwi', 'cherry')
```

### Add Items

#### Method 1: Convert to List
```python
thistuple = ("apple", "banana", "cherry")
y = list(thistuple)
y.append("orange")
thistuple = tuple(y)
print(thistuple)  # ('apple', 'banana', 'cherry', 'orange')
```

#### Method 2: Add Tuple to Tuple
```python
thistuple = ("apple", "banana", "cherry")
y = ("orange",)  # Note the comma!
thistuple += y
print(thistuple)  # ('apple', 'banana', 'cherry', 'orange')
```

### Remove Items

#### Method 1: Convert to List
```python
thistuple = ("apple", "banana", "cherry")
y = list(thistuple)
y.remove("apple")
thistuple = tuple(y)
print(thistuple)  # ('banana', 'cherry')
```

#### Method 2: Delete Entire Tuple
```python
thistuple = ("apple", "banana", "cherry")
del thistuple
# print(thistuple)  # This will raise an error - tuple no longer exists
```

---

## Unpack Tuples

**Definition:** Extracting tuple values back into variables.

### Basic Unpacking
```python
# Packing
fruits = ("apple", "banana", "cherry")

# Unpacking
(green, yellow, red) = fruits
print(green)   # apple
print(yellow)  # banana
print(red)     # cherry
```

**Note:** Number of variables must match number of values!

### Using Asterisk (*)

#### Collect Remaining Values
```python
fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")
(green, yellow, *red) = fruits

print(green)   # apple
print(yellow)  # banana
print(red)     # ['cherry', 'strawberry', 'raspberry']
```

#### Asterisk in Middle
```python
fruits = ("apple", "mango", "papaya", "pineapple", "cherry")
(green, *tropic, red) = fruits

print(green)   # apple
print(tropic)  # ['mango', 'papaya', 'pineapple']
print(red)     # cherry
```

---

## Loop Through Tuples

### For Loop
```python
thistuple = ("apple", "banana", "cherry")
for x in thistuple:
    print(x)
```

### Loop Through Index Numbers
```python
thistuple = ("apple", "banana", "cherry")
for i in range(len(thistuple)):
    print(thistuple[i])
```

### While Loop
```python
thistuple = ("apple", "banana", "cherry")
i = 0
while i < len(thistuple):
    print(thistuple[i])
    i += 1
```

---

## Join Tuples

### Using + Operator
```python
tuple1 = ("a", "b", "c")
tuple2 = (1, 2, 3)
tuple3 = tuple1 + tuple2
print(tuple3)  # ('a', 'b', 'c', 1, 2, 3)
```

### Multiply Tuples
```python
fruits = ("apple", "banana", "cherry")
mytuple = fruits * 2
print(mytuple)  # ('apple', 'banana', 'cherry', 'apple', 'banana', 'cherry')
```

---

## Tuple Methods

**Python has only 2 built-in methods for tuples:**

| Method | Description | Syntax | Example |
|--------|-------------|--------|---------|
| `count()` | Returns number of occurrences | `tuple.count(value)` | `tuple.count("apple")` |
| `index()` | Returns first index of value | `tuple.index(value)` | `tuple.index("banana")` |

### Examples
```python
thistuple = ("apple", "banana", "cherry", "apple", "cherry")

# count() - count occurrences
print(thistuple.count("apple"))   # Output: 2
print(thistuple.count("cherry"))  # Output: 2

# index() - find position
print(thistuple.index("banana"))  # Output: 1
print(thistuple.index("cherry"))  # Output: 2 (first occurrence)
```

---

## Tuple vs List Comparison

| Feature | Tuple | List |
|---------|-------|------|
| **Syntax** | `()` | `[]` |
| **Mutable** | ❌ No | ✅ Yes |
| **Speed** | Faster | Slower |
| **Memory** | Less | More |
| **Methods** | 2 methods | 11 methods |
| **Use Case** | Fixed data | Dynamic data |

### When to Use Tuples
- Data should **not change**
- Need **faster** performance
- Want to **protect** data from modification
- Using as **dictionary keys** (tuples can, lists cannot)

### When to Use Lists
- Data needs to **change frequently**
- Need to **add/remove** items
- Need **more methods** (sort, append, etc.)

---

## Practical Examples

### Example 1: Coordinates
```python
# Tuples perfect for fixed coordinates
point = (10, 20)
x, y = point
print(f"X: {x}, Y: {y}")
```

### Example 2: RGB Colors
```python
red = (255, 0, 0)
green = (0, 255, 0)
blue = (0, 0, 255)

r, g, b = red
print(f"Red: R={r}, G={g}, B={b}")
```

### Example 3: Database Records
```python
# Tuple for unchangeable record
student = ("John", 25, "Computer Science", 3.8)
name, age, major, gpa = student
print(f"{name} is {age} years old, majoring in {major}")
```

### Example 4: Function Return Multiple Values
```python
def get_user_info():
    return ("Alice", 30, "alice@email.com")

name, age, email = get_user_info()
print(f"Name: {name}, Age: {age}, Email: {email}")
```

---

## Key Takeaways

### ✅ Remember
- Tuples use **round brackets** `()`
- Tuples are **ordered and unchangeable**
- **One-item tuple** needs comma: `("item",)`
- **Index starts at 0**
- **Negative indexing** from end (-1 is last)
- Only **2 methods**: `count()` and `index()`

### 🎯 Key Differences from Lists
- **Immutable** - cannot change after creation
- **Faster** than lists
- **Less memory** than lists
- **Fewer methods** than lists
- Can be used as **dictionary keys**

### ⚠️ Common Mistakes
- Forgetting comma in one-item tuple
- Trying to modify tuple directly
- Confusing tuple with list syntax

---

**Tuples are perfect for data that shouldn't change - use them for fixed collections!**