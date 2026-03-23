# Python Sets

## What are Sets?

**Definition:** Sets are used to store multiple items in a single variable. Sets are unordered, unchangeable*, and do not allow duplicates.

*Note: Set items are unchangeable, but you can remove and add new items.

```python
myset = {"apple", "banana", "cherry"}
print(myset)  # Output: {'apple', 'banana', 'cherry'}
```

---

## Set Characteristics

| Property | Description | Example |
|----------|-------------|---------|
| **Unordered** | Items have no defined order | Order may change each time |
| **Unchangeable** | Cannot change items after creation | Can add/remove, not modify |
| **No Duplicates** | Cannot have two items with same value | Duplicates are ignored |
| **Unindexed** | Cannot access by index | No `set[0]` |

---

## Creating Sets

### Using Curly Brackets
```python
thisset = {"apple", "banana", "cherry"}
print(thisset)
```

### Using set() Constructor
```python
thisset = set(("apple", "banana", "cherry"))  # Note double parentheses
print(thisset)
```

### Different Data Types
```python
set1 = {"apple", "banana", "cherry"}       # Strings
set2 = {1, 5, 7, 9, 3}                     # Integers
set3 = {True, False, False}                # Booleans
set4 = {"abc", 34, True, 40, "male"}       # Mixed types
```

---

## Set Properties

### No Duplicates
```python
thisset = {"apple", "banana", "cherry", "apple"}
print(thisset)  # Output: {'apple', 'banana', 'cherry'} - duplicate removed
```

### True and 1 are Same
```python
thisset = {"apple", "banana", "cherry", True, 1, 2}
print(thisset)  # Output: {'apple', 'banana', 'cherry', True, 2} - 1 is duplicate of True
```

### False and 0 are Same
```python
thisset = {"apple", "banana", "cherry", False, True, 0}
print(thisset)  # Output: {'apple', 'banana', 'cherry', False, True} - 0 is duplicate of False
```

### Set Length
```python
thisset = {"apple", "banana", "cherry"}
print(len(thisset))  # Output: 3
```

### Set Type
```python
myset = {"apple", "banana", "cherry"}
print(type(myset))  # Output: <class 'set'>
```

---

## Collections Comparison

| Collection | Ordered | Changeable | Duplicates | Indexed | Syntax |
|------------|---------|------------|------------|---------|--------|
| **List** | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes | `[]` |
| **Tuple** | ✅ Yes | ❌ No | ✅ Yes | ✅ Yes | `()` |
| **Set** | ❌ No | ✅ Yes* | ❌ No | ❌ No | `{}` |
| **Dictionary** | ✅ Yes** | ✅ Yes | ❌ No | ✅ Yes | `{"key": "value"}` |

*Can add/remove items, not change  
**Ordered since Python 3.7

---

## Access Set Items

**Important:** Cannot access items by index or key!

### Loop Through Set
```python
thisset = {"apple", "banana", "cherry"}
for x in thisset:
    print(x)
```

### Check if Item Exists
```python
thisset = {"apple", "banana", "cherry"}
print("banana" in thisset)      # True
print("banana" not in thisset)  # False
```

---

## Add Set Items

| Method | Description | Syntax |
|--------|-------------|--------|
| `add()` | Adds one item | `set.add("orange")` |
| `update()` | Adds multiple items from iterable | `set.update(set2)` |

### add() - Add One Item
```python
thisset = {"apple", "banana", "cherry"}
thisset.add("orange")
print(thisset)  # {'apple', 'banana', 'cherry', 'orange'}
```

### update() - Add Multiple Items
```python
# Add from another set
thisset = {"apple", "banana", "cherry"}
tropical = {"pineapple", "mango", "papaya"}
thisset.update(tropical)
print(thisset)  # {'apple', 'banana', 'cherry', 'pineapple', 'mango', 'papaya'}

# Add from list
thisset = {"apple", "banana", "cherry"}
mylist = ["kiwi", "orange"]
thisset.update(mylist)
print(thisset)  # {'apple', 'banana', 'cherry', 'kiwi', 'orange'}
```

---

## Remove Set Items

| Method | Description | Error if Not Found |
|--------|-------------|--------------------|
| `remove()` | Removes specified item | ✅ Yes |
| `discard()` | Removes specified item | ❌ No |
| `pop()` | Removes random item | N/A |
| `clear()` | Empties the set | N/A |
| `del` | Deletes the set completely | N/A |

### Examples
```python
# remove() - raises error if not found
thisset = {"apple", "banana", "cherry"}
thisset.remove("banana")
print(thisset)  # {'apple', 'cherry'}

# discard() - no error if not found
thisset = {"apple", "banana", "cherry"}
thisset.discard("banana")
print(thisset)  # {'apple', 'cherry'}

# pop() - removes random item
thisset = {"apple", "banana", "cherry"}
x = thisset.pop()
print(x)        # Random item removed
print(thisset)  # Remaining items

# clear() - empties set
thisset = {"apple", "banana", "cherry"}
thisset.clear()
print(thisset)  # set()

# del - deletes set completely
thisset = {"apple", "banana", "cherry"}
del thisset
# print(thisset)  # Error - set no longer exists
```

---

## Loop Sets

### For Loop
```python
thisset = {"apple", "banana", "cherry"}
for x in thisset:
    print(x)
```

---

## Join Sets

### Set Operations Summary

| Operation | Method | Operator | Description |
|-----------|--------|----------|-------------|
| **Union** | `union()` | `\|` | All items from both sets |
| **Intersection** | `intersection()` | `&` | Only common items |
| **Difference** | `difference()` | `-` | Items in first, not in second |
| **Symmetric Difference** | `symmetric_difference()` | `^` | Items not in both |

---

### Union - All Items

**Definition:** Combines all items from both sets (no duplicates).

```python
# Using union()
set1 = {"a", "b", "c"}
set2 = {1, 2, 3}
set3 = set1.union(set2)
print(set3)  # {'a', 'b', 'c', 1, 2, 3}

# Using | operator
set3 = set1 | set2
print(set3)  # {'a', 'b', 'c', 1, 2, 3}

# Multiple sets
set1 = {"a", "b", "c"}
set2 = {1, 2, 3}
set3 = {"John", "Elena"}
myset = set1.union(set2, set3)
print(myset)  # {'a', 'b', 'c', 1, 2, 3, 'John', 'Elena'}

# With tuple
x = {"a", "b", "c"}
y = (1, 2, 3)
z = x.union(y)
print(z)  # {'a', 'b', 'c', 1, 2, 3}
```

### update() - Modify Original
```python
set1 = {"a", "b", "c"}
set2 = {1, 2, 3}
set1.update(set2)
print(set1)  # {'a', 'b', 'c', 1, 2, 3}
```

---

### Intersection - Only Common Items

**Definition:** Keeps only items present in both sets.

```python
# Using intersection()
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1.intersection(set2)
print(set3)  # {'apple'}

# Using & operator
set3 = set1 & set2
print(set3)  # {'apple'}

# intersection_update() - modifies original
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set1.intersection_update(set2)
print(set1)  # {'apple'}
```

---

### Difference - Items in First Only

**Definition:** Keeps items from first set that are not in second set.

```python
# Using difference()
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1.difference(set2)
print(set3)  # {'banana', 'cherry'}

# Using - operator
set3 = set1 - set2
print(set3)  # {'banana', 'cherry'}

# difference_update() - modifies original
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set1.difference_update(set2)
print(set1)  # {'banana', 'cherry'}
```

---

### Symmetric Difference - Items Not in Both

**Definition:** Keeps items that are NOT present in both sets.

```python
# Using symmetric_difference()
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1.symmetric_difference(set2)
print(set3)  # {'banana', 'cherry', 'google', 'microsoft'}

# Using ^ operator
set3 = set1 ^ set2
print(set3)  # {'banana', 'cherry', 'google', 'microsoft'}

# symmetric_difference_update() - modifies original
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set1.symmetric_difference_update(set2)
print(set1)  # {'banana', 'cherry', 'google', 'microsoft'}
```

---

## Frozenset

**Definition:** Immutable version of a set. Cannot add or remove elements.

### Creating Frozenset
```python
x = frozenset({"apple", "banana", "cherry"})
print(x)         # frozenset({'apple', 'banana', 'cherry'})
print(type(x))   # <class 'frozenset'>
```

### Frozenset Methods

| Method | Operator | Description |
|--------|----------|-------------|
| `copy()` | - | Returns a shallow copy |
| `difference()` | `-` | Returns difference |
| `intersection()` | `&` | Returns intersection |
| `isdisjoint()` | - | Checks if no common items |
| `issubset()` | `<=` / `<` | Checks if subset |
| `issuperset()` | `>=` | `>` | Checks if superset |
| `symmetric_difference()` | `^` | Returns symmetric difference |
| `union()` | `\|` | Returns union |

---

## Set Methods Reference

| Method | Operator | Description |
|--------|----------|-------------|
| `add()` | - | Adds an element |
| `clear()` | - | Removes all elements |
| `copy()` | - | Returns a copy |
| `difference()` | `-` | Returns difference between sets |
| `difference_update()` | `-=` | Removes items also in another set |
| `discard()` | - | Removes specified item (no error) |
| `intersection()` | `&` | Returns intersection |
| `intersection_update()` | `&=` | Keeps only common items |
| `isdisjoint()` | - | Checks if no intersection |
| `issubset()` | `<=` / `<` | Checks if subset |
| `issuperset()` | `>=` / `>` | Checks if superset |
| `pop()` | - | Removes random element |
| `remove()` | - | Removes specified element (error if not found) |
| `symmetric_difference()` | `^` | Returns items not in both |
| `symmetric_difference_update()` | `^=` | Keeps items not in both |
| `union()` | `\|` | Returns union of sets |
| `update()` | `\|=` | Adds items from another set |

---

## Practical Examples

### Example 1: Remove Duplicates
```python
mylist = [1, 2, 2, 3, 3, 3, 4, 5, 5]
unique = set(mylist)
print(unique)  # {1, 2, 3, 4, 5}
```

### Example 2: Common Elements
```python
students_math = {"Alice", "Bob", "Charlie", "David"}
students_science = {"Bob", "David", "Eve", "Frank"}
both_classes = students_math.intersection(students_science)
print(both_classes)  # {'Bob', 'David'}
```

### Example 3: Unique to Each
```python
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
unique_to_set1 = set1.difference(set2)
print(unique_to_set1)  # {'banana', 'cherry'}
```

---

## Key Takeaways

### ✅ Remember
- Sets use **curly brackets** `{}`
- Sets are **unordered, unchangeable*, no duplicates**
- **Cannot access by index**
- **True = 1** and **False = 0** in sets
- Use **for loop** to access items
- **Frozenset** is immutable version

### 🎯 Common Operations
- **Add**: `add()`, `update()`
- **Remove**: `remove()`, `discard()`, `pop()`, `clear()`
- **Join**: `union()`, `intersection()`, `difference()`, `symmetric_difference()`
- **Check**: `in`, `not in`

### 🔧 When to Use Sets
- **Remove duplicates** from list
- **Fast membership testing** (`in` operator)
- **Mathematical set operations** (union, intersection)
- **Unique collections** of items

---

**Sets are perfect for unique collections and mathematical set operations!**