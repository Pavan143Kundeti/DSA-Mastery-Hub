# Python Iterators

## What is an Iterator?

**Definition:** An iterator is an object that contains countable values and can be iterated upon (traversed through all values).

**Technical:** An object that implements the iterator protocol with `__iter__()` and `__next__()` methods.

---

## Iterator vs Iterable

| Term | Definition | Examples |
|------|------------|----------|
| **Iterable** | Object you can iterate over | Lists, tuples, dicts, sets, strings |
| **Iterator** | Object that produces values one at a time | Result of `iter()` function |

---

## Getting an Iterator

Use `iter()` function to get an iterator from iterable objects.

### From Tuple
```python
mytuple = ("apple", "banana", "cherry")
myit = iter(mytuple)

print(next(myit))  # Output: apple
print(next(myit))  # Output: banana
print(next(myit))  # Output: cherry
```

### From String
```python
mystr = "banana"
myit = iter(mystr)

print(next(myit))  # Output: b
print(next(myit))  # Output: a
print(next(myit))  # Output: n
print(next(myit))  # Output: a
print(next(myit))  # Output: n
print(next(myit))  # Output: a
```

---

## Looping Through an Iterator

### Manual Iteration
```python
mytuple = ("apple", "banana", "cherry")
myit = iter(mytuple)

for x in myit:
    print(x)
# Output: apple, banana, cherry
```

### For Loop (Automatic)
```python
mytuple = ("apple", "banana", "cherry")

for x in mytuple:
    print(x)
# Output: apple, banana, cherry
```

**Note:** For loop automatically creates an iterator and calls `next()` for each loop.

---

## Creating Custom Iterator

To create an iterator, implement `__iter__()` and `__next__()` methods.

### Basic Iterator Class
```python
class MyNumbers:
    def __iter__(self):
        self.a = 1
        return self
    
    def __next__(self):
        x = self.a
        self.a += 1
        return x

myclass = MyNumbers()
myiter = iter(myclass)

print(next(myiter))  # Output: 1
print(next(myiter))  # Output: 2
print(next(myiter))  # Output: 3
print(next(myiter))  # Output: 4
print(next(myiter))  # Output: 5
```

---

## Iterator Protocol Methods

| Method | Purpose | Must Return |
|--------|---------|-------------|
| `__iter__()` | Initialize iterator | Iterator object (self) |
| `__next__()` | Get next value | Next item in sequence |

### Method Details

#### `__iter__()` Method
- Acts like `__init__()` for iterators
- Can do initialization operations
- Must always return the iterator object itself

#### `__next__()` Method
- Returns the next item in sequence
- Can do operations before returning
- Must raise `StopIteration` when done

---

## StopIteration

**Problem:** Without stopping condition, iterator continues forever.

**Solution:** Use `StopIteration` exception to stop iteration.

### Iterator with Stop Condition
```python
class MyNumbers:
    def __iter__(self):
        self.a = 1
        return self
    
    def __next__(self):
        if self.a <= 20:
            x = self.a
            self.a += 1
            return x
        else:
            raise StopIteration

myclass = MyNumbers()
myiter = iter(myclass)

for x in myiter:
    print(x)
# Output: 1, 2, 3, ..., 20
```

---

## Practical Examples

### Even Numbers Iterator
```python
class EvenNumbers:
    def __iter__(self):
        self.num = 0
        return self
    
    def __next__(self):
        if self.num < 10:
            result = self.num
            self.num += 2
            return result
        else:
            raise StopIteration

evens = EvenNumbers()
for x in evens:
    print(x)
# Output: 0, 2, 4, 6, 8
```

### Countdown Iterator
```python
class Countdown:
    def __init__(self, start):
        self.start = start
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.start > 0:
            result = self.start
            self.start -= 1
            return result
        else:
            raise StopIteration

countdown = Countdown(5)
for x in countdown:
    print(x)
# Output: 5, 4, 3, 2, 1
```

---

## Built-in Iterators

### iter() Function
```python
# Get iterator from iterable
my_list = [1, 2, 3]
my_iter = iter(my_list)
```

### next() Function
```python
# Get next value from iterator
print(next(my_iter))  # 1
print(next(my_iter))  # 2
print(next(my_iter))  # 3
# next(my_iter)  # Raises StopIteration
```

---

## Iterator vs Generator

| Feature | Iterator | Generator |
|---------|----------|-----------|
| Definition | Class with `__iter__` and `__next__` | Function with `yield` |
| Code | More code | Less code |
| Memory | Stores state in variables | Automatic state management |
| Use case | Complex iteration logic | Simple iteration |

---

## Quick Reference

### Create Iterator
```python
class MyIterator:
    def __iter__(self):
        # Initialize
        return self
    
    def __next__(self):
        # Return next value or raise StopIteration
        pass
```

### Use Iterator
```python
obj = MyIterator()
iterator = iter(obj)
value = next(iterator)
```

---

## Key Takeaways

### ✅ Remember
- **Iterator** produces values one at a time
- **Iterable** can be iterated over (lists, strings, etc.)
- **`__iter__()`** returns iterator object
- **`__next__()`** returns next value
- **`StopIteration`** stops the iteration
- **`iter()`** gets iterator from iterable
- **`next()`** gets next value from iterator
- **For loops** use iterators automatically

### 🎯 Interview Important
- Difference between iterator and iterable
- Iterator protocol methods (`__iter__`, `__next__`)
- When to raise StopIteration
- How for loops work with iterators
- Iterator vs generator comparison
- Memory efficiency of iterators

---

**Use iterators for memory-efficient, lazy evaluation of sequences!**