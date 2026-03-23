# Python Lists

## What are Lists?

**Definition:** Lists are used to store multiple items in a single variable. Lists are ordered, changeable, and allow duplicate values.

```python
mylist = ["apple", "banana", "cherry"]
print(mylist)  # Output: ['apple', 'banana', 'cherry']
```

---

## List Characteristics

| Property | Description | Example |
|----------|-------------|---------|
| **Ordered** | Items have a defined order that won't change | `[1, 2, 3]` stays `[1, 2, 3]` |
| **Changeable** | Can add, remove, or modify items | Can change `"apple"` to `"kiwi"` |
| **Allow Duplicates** | Can have items with same value | `["apple", "apple"]` is valid |
| **Indexed** | First item is `[0]`, second is `[1]` | `mylist[0]` gets first item |

---

## Creating Lists

### Using Square Brackets
```python
thislist = ["apple", "banana", "cherry"]
print(thislist)
```

### Using list() Constructor
```python
thislist = list(("apple", "banana", "cherry"))  # Note double parentheses
print(thislist)
```

### Different Data Types
```python
list1 = ["apple", "banana", "cherry"]        # Strings
list2 = [1, 5, 7, 9, 3]                      # Integers
list3 = [True, False, False]                 # Booleans
list4 = ["abc", 34, True, 40, "male"]        # Mixed types
```

---

## List Properties

### List Length
```python
thislist = ["apple", "banana", "cherry"]
print(len(thislist))  # Output: 3
```

### List Type
```python
mylist = ["apple", "banana", "cherry"]
print(type(mylist))  # Output: <class 'list'>
```

### Allow Duplicates
```python
thislist = ["apple", "banana", "cherry", "apple", "cherry"]
print(thislist)  # Duplicates are allowed
```

---

## Python Collections Comparison

| Collection | Ordered | Changeable | Duplicates | Syntax |
|------------|---------|------------|------------|--------|
| **List** | ✅ Yes | ✅ Yes | ✅ Yes | `[]` |
| **Tuple** | ✅ Yes | ❌ No | ✅ Yes | `()` |
| **Set** | ❌ No | ✅ Yes* | ❌ No | `{}` |
| **Dictionary** | ✅ Yes** | ✅ Yes | ❌ No | `{"key": "value"}` |

*Set items unchangeable, but can add/remove  
**Ordered since Python 3.7

---

## Access List Items

### By Index
```python
thislist = ["apple", "banana", "cherry"]
print(thislist[0])   # Output: apple
print(thislist[1])   # Output: banana
print(thislist[2])   # Output: cherry
```

### Negative Indexing
```python
thislist = ["apple", "banana", "cherry"]
print(thislist[-1])  # Output: cherry (last item)
print(thislist[-2])  # Output: banana (second last)
print(thislist[-3])  # Output: apple (third last)
```

### Range of Indexes (Slicing)

| Syntax | Description | Example | Result |
|--------|-------------|---------|--------|
| `[start:end]` | From start to end-1 | `[2:5]` | Items 2, 3, 4 |
| `[:end]` | From beginning to end-1 | `[:4]` | Items 0, 1, 2, 3 |
| `[start:]` | From start to end | `[2:]` | Items 2 to last |
| `[-start:-end]` | Negative range | `[-4:-1]` | Last 4 to last 1 |

```python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]

print(thislist[2:5])    # ['cherry', 'orange', 'kiwi']
print(thislist[:4])     # ['apple', 'banana', 'cherry', 'orange']
print(thislist[2:])     # ['cherry', 'orange', 'kiwi', 'melon', 'mango']
print(thislist[-4:-1])  # ['orange', 'kiwi', 'melon']
```

### Check if Item Exists
```python
thislist = ["apple", "banana", "cherry"]
if "apple" in thislist:
    print("Yes, 'apple' is in the list")
```

---

## Change List Items

### Change Single Item
```python
thislist = ["apple", "banana", "cherry"]
thislist[1] = "blackcurrant"
print(thislist)  # ['apple', 'blackcurrant', 'cherry']
```

### Change Range of Items
```python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]
thislist[1:3] = ["blackcurrant", "watermelon"]
print(thislist)  # ['apple', 'blackcurrant', 'watermelon', 'orange', 'kiwi', 'mango']
```

### Insert More Items Than Replace
```python
thislist = ["apple", "banana", "cherry"]
thislist[1:2] = ["blackcurrant", "watermelon"]
print(thislist)  # ['apple', 'blackcurrant', 'watermelon', 'cherry']
```

### Insert Fewer Items Than Replace
```python
thislist = ["apple", "banana", "cherry"]
thislist[1:3] = ["watermelon"]
print(thislist)  # ['apple', 'watermelon']
```

---

## Add List Items

### append() - Add to End
```python
thislist = ["apple", "banana", "cherry"]
thislist.append("orange")
print(thislist)  # ['apple', 'banana', 'cherry', 'orange']
```

### insert() - Add at Position
```python
thislist = ["apple", "banana", "cherry"]
thislist.insert(1, "orange")
print(thislist)  # ['apple', 'orange', 'banana', 'cherry']
```

### extend() - Add Another List
```python
thislist = ["apple", "banana", "cherry"]
tropical = ["mango", "pineapple", "papaya"]
thislist.extend(tropical)
print(thislist)  # ['apple', 'banana', 'cherry', 'mango', 'pineapple', 'papaya']
```

### extend() - Add Any Iterable
```python
thislist = ["apple", "banana", "cherry"]
thistuple = ("kiwi", "orange")
thislist.extend(thistuple)
print(thislist)  # ['apple', 'banana', 'cherry', 'kiwi', 'orange']
```

---

## Remove List Items

| Method | Description | Example |
|--------|-------------|---------|
| `remove(item)` | Removes specified item | `list.remove("banana")` |
| `pop(index)` | Removes item at index | `list.pop(1)` |
| `pop()` | Removes last item | `list.pop()` |
| `del list[index]` | Deletes item at index | `del list[0]` |
| `del list` | Deletes entire list | `del list` |
| `clear()` | Empties the list | `list.clear()` |

### Examples
```python
# remove() - removes specified item
thislist = ["apple", "banana", "cherry"]
thislist.remove("banana")
print(thislist)  # ['apple', 'cherry']

# pop() - removes by index
thislist = ["apple", "banana", "cherry"]
thislist.pop(1)
print(thislist)  # ['apple', 'cherry']

# pop() - removes last item
thislist = ["apple", "banana", "cherry"]
thislist.pop()
print(thislist)  # ['apple', 'banana']

# del - removes by index
thislist = ["apple", "banana", "cherry"]
del thislist[0]
print(thislist)  # ['banana', 'cherry']

# clear() - empties list
thislist = ["apple", "banana", "cherry"]
thislist.clear()
print(thislist)  # []
```

---

## Loop Through Lists

### For Loop
```python
thislist = ["apple", "banana", "cherry"]
for x in thislist:
    print(x)
```

### Loop Through Index Numbers
```python
thislist = ["apple", "banana", "cherry"]
for i in range(len(thislist)):
    print(thislist[i])
```

### While Loop
```python
thislist = ["apple", "banana", "cherry"]
i = 0
while i < len(thislist):
    print(thislist[i])
    i += 1
```

### List Comprehension (Shortest)
```python
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]
```

---

## List Comprehension

**Definition:** Shorter syntax to create new lists based on existing lists.

### Syntax
```
newlist = [expression for item in iterable if condition]
```

### Without List Comprehension
```python
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = []
for x in fruits:
    if "a" in x:
        newlist.append(x)
print(newlist)  # ['apple', 'banana', 'mango']
```

### With List Comprehension
```python
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = [x for x in fruits if "a" in x]
print(newlist)  # ['apple', 'banana', 'mango']
```

### More Examples
```python
# With condition
newlist = [x for x in fruits if x != "apple"]

# Without condition
newlist = [x for x in fruits]

# With range
newlist = [x for x in range(10)]

# With range and condition
newlist = [x for x in range(10) if x < 5]

# Modify expression
newlist = [x.upper() for x in fruits]

# Set all to same value
newlist = ['hello' for x in fruits]

# Conditional expression
newlist = [x if x != "banana" else "orange" for x in fruits]
```

---

## Sort Lists

### sort() - Ascending Order
```python
# Alphabetically
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort()
print(thislist)  # ['banana', 'kiwi', 'mango', 'orange', 'pineapple']

# Numerically
thislist = [100, 50, 65, 82, 23]
thislist.sort()
print(thislist)  # [23, 50, 65, 82, 100]
```

### sort(reverse=True) - Descending Order
```python
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort(reverse=True)
print(thislist)  # ['pineapple', 'orange', 'mango', 'kiwi', 'banana']
```

### Custom Sort Function
```python
def myfunc(n):
    return abs(n - 50)

thislist = [100, 50, 65, 82, 23]
thislist.sort(key=myfunc)
print(thislist)  # [50, 65, 23, 82, 100]
```

### Case-Insensitive Sort
```python
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.sort(key=str.lower)
print(thislist)  # ['banana', 'cherry', 'Kiwi', 'Orange']
```

### reverse() - Reverse Order
```python
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.reverse()
print(thislist)  # ['cherry', 'Kiwi', 'Orange', 'banana']
```

---

## Copy Lists

**Important:** `list2 = list1` creates a reference, not a copy!

| Method | Syntax | Description |
|--------|--------|-------------|
| `copy()` | `list2 = list1.copy()` | Creates a copy |
| `list()` | `list2 = list(list1)` | Creates a copy |
| Slice `[:]` | `list2 = list1[:]` | Creates a copy |

### Examples
```python
# Using copy()
thislist = ["apple", "banana", "cherry"]
mylist = thislist.copy()

# Using list()
thislist = ["apple", "banana", "cherry"]
mylist = list(thislist)

# Using slice operator
thislist = ["apple", "banana", "cherry"]
mylist = thislist[:]
```

---

## Join Lists

| Method | Syntax | Description |
|--------|--------|-------------|
| `+` operator | `list3 = list1 + list2` | Concatenate lists |
| `append()` loop | `for x in list2: list1.append(x)` | Append each item |
| `extend()` | `list1.extend(list2)` | Add list2 to list1 |

### Examples
```python
# Using + operator
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]
list3 = list1 + list2
print(list3)  # ['a', 'b', 'c', 1, 2, 3]

# Using append() in loop
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]
for x in list2:
    list1.append(x)
print(list1)  # ['a', 'b', 'c', 1, 2, 3]

# Using extend()
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]
list1.extend(list2)
print(list1)  # ['a', 'b', 'c', 1, 2, 3]
```

---

## List Methods Reference

| Method | Description | Example |
|--------|-------------|---------|
| `append(item)` | Adds item at end | `list.append("orange")` |
| `clear()` | Removes all items | `list.clear()` |
| `copy()` | Returns a copy | `newlist = list.copy()` |
| `count(item)` | Counts occurrences | `list.count("apple")` |
| `extend(iterable)` | Adds iterable items | `list.extend(list2)` |
| `index(item)` | Returns first index | `list.index("banana")` |
| `insert(pos, item)` | Inserts at position | `list.insert(1, "kiwi")` |
| `pop(index)` | Removes and returns item | `list.pop(1)` |
| `remove(item)` | Removes first occurrence | `list.remove("apple")` |
| `reverse()` | Reverses order | `list.reverse()` |
| `sort()` | Sorts list | `list.sort()` |

---

## Key Takeaways

### ✅ Remember
- Lists use **square brackets** `[]`
- Lists are **ordered, changeable, allow duplicates**
- **Index starts at 0**
- **Negative indexing** starts from end (-1 is last)
- Use **slicing** for ranges `[start:end]`
- **List comprehension** for concise code

### 🎯 Common Operations
- **Add**: `append()`, `insert()`, `extend()`
- **Remove**: `remove()`, `pop()`, `clear()`, `del`
- **Modify**: Direct assignment `list[0] = "new"`
- **Copy**: `copy()`, `list()`, `[:]`
- **Join**: `+`, `extend()`
- **Sort**: `sort()`, `reverse()`

---

**Lists are one of the most versatile and commonly used data structures in Python!**