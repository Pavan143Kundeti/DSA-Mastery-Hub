# Python Arrays

## Important Note

**Python does not have built-in Arrays.** Python **Lists** are used as Arrays.

For true arrays, import libraries like **NumPy**.

---

## What is an Array?

**Definition:** A special variable that can hold multiple values under a single name.

### Without Arrays (Bad)
```python
car1 = "Ford"
car2 = "Volvo"
car3 = "BMW"
```

### With Arrays (Good)
```python
cars = ["Ford", "Volvo", "BMW"]
```

**Benefits:** Easy to loop through, manage hundreds of items.

---

## Creating Arrays (Lists)

```python
cars = ["Ford", "Volvo", "BMW"]
```

---

## Access Array Elements

Use index numbers (starting from 0).

```python
cars = ["Ford", "Volvo", "BMW"]

x = cars[0]  # Output: Ford
print(cars[1])  # Output: Volvo
```

### Modify Elements
```python
cars[0] = "Toyota"
print(cars)  # Output: ['Toyota', 'Volvo', 'BMW']
```

---

## Array Length

Use `len()` to get number of elements.

```python
cars = ["Ford", "Volvo", "BMW"]
x = len(cars)
print(x)  # Output: 3
```

**Note:** Length is always one more than highest index.

---

## Looping Array Elements

```python
cars = ["Ford", "Volvo", "BMW"]

for x in cars:
    print(x)

# Output:
# Ford
# Volvo
# BMW
```

---

## Adding Elements

### append() - Add at End
```python
cars = ["Ford", "Volvo", "BMW"]
cars.append("Honda")
print(cars)  # Output: ['Ford', 'Volvo', 'BMW', 'Honda']
```

### insert() - Add at Position
```python
cars = ["Ford", "Volvo", "BMW"]
cars.insert(1, "Toyota")
print(cars)  # Output: ['Ford', 'Toyota', 'Volvo', 'BMW']
```

---

## Removing Elements

### pop() - Remove by Index
```python
cars = ["Ford", "Volvo", "BMW"]
cars.pop(1)  # Remove index 1 (Volvo)
print(cars)  # Output: ['Ford', 'BMW']
```

### remove() - Remove by Value
```python
cars = ["Ford", "Volvo", "BMW"]
cars.remove("Volvo")
print(cars)  # Output: ['Ford', 'BMW']
```

**Note:** `remove()` only removes first occurrence.

---

## Array Methods Table

| Method | Description | Example |
|--------|-------------|---------|
| `append()` | Add element at end | `cars.append("Honda")` |
| `clear()` | Remove all elements | `cars.clear()` |
| `copy()` | Return copy of list | `new_cars = cars.copy()` |
| `count()` | Count occurrences | `cars.count("Ford")` |
| `extend()` | Add elements from iterable | `cars.extend(["Honda", "Toyota"])` |
| `index()` | Find index of value | `cars.index("BMW")` |
| `insert()` | Add at specific position | `cars.insert(1, "Toyota")` |
| `pop()` | Remove by index | `cars.pop(1)` |
| `remove()` | Remove by value | `cars.remove("Ford")` |
| `reverse()` | Reverse order | `cars.reverse()` |
| `sort()` | Sort list | `cars.sort()` |

---

## Method Examples

### count()
```python
cars = ["Ford", "BMW", "Ford", "Toyota"]
print(cars.count("Ford"))  # Output: 2
```

### extend()
```python
cars = ["Ford", "BMW"]
more_cars = ["Toyota", "Honda"]
cars.extend(more_cars)
print(cars)  # Output: ['Ford', 'BMW', 'Toyota', 'Honda']
```

### index()
```python
cars = ["Ford", "BMW", "Toyota"]
print(cars.index("BMW"))  # Output: 1
```

### reverse()
```python
cars = ["Ford", "BMW", "Toyota"]
cars.reverse()
print(cars)  # Output: ['Toyota', 'BMW', 'Ford']
```

### sort()
```python
cars = ["Ford", "BMW", "Toyota"]
cars.sort()
print(cars)  # Output: ['BMW', 'Ford', 'Toyota']
```

---

## Quick Reference

### Basic Operations
```python
# Create
arr = [1, 2, 3]

# Access
arr[0]  # First element

# Modify
arr[0] = 10

# Length
len(arr)

# Add
arr.append(4)

# Remove
arr.pop(0)  # By index
arr.remove(2)  # By value
```

---

## Key Takeaways

### ✅ Remember
- **Python uses Lists as Arrays**
- **Index starts from 0**
- **len()** gets array length
- **append()** adds at end
- **pop()** removes by index
- **remove()** removes by value
- **For true arrays, use NumPy**

### 🎯 Interview Important
- Python has no built-in arrays (uses lists)
- Difference between pop() and remove()
- Array indexing starts at 0
- Common array methods
- When to use NumPy arrays vs lists

---

**Use Python lists as arrays for basic operations, NumPy for advanced array operations!**