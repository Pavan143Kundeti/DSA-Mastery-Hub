# Python While Loops

## What are Loops?

**Definition:** Loops are used to execute a block of code repeatedly as long as a condition is true.

Python has two types of loops:
1. **while loops** - Repeat while condition is true
2. **for loops** - Iterate over a sequence

---

## The While Loop

**Definition:** The while loop executes a set of statements as long as a condition is true.

### Syntax
```python
while condition:
    statement
```

### Basic Example
```python
i = 1

while i < 6:
    print(i)
    i += 1

# Output:
# 1
# 2
# 3
# 4
# 5
```

---

## How While Loop Works

| Step | Action |
|------|--------|
| 1 | Check condition |
| 2 | If True, execute code block |
| 3 | Repeat from step 1 |
| 4 | If False, exit loop |

### Flow Diagram
```
Start → Check Condition → True → Execute Code → Back to Check
                ↓
              False
                ↓
              Exit Loop
```

---

## Important: Increment Variable

**Warning:** Always increment the loop variable, or the loop will run forever (infinite loop).

### Correct (With Increment)
```python
i = 1

while i < 6:
    print(i)
    i += 1  # Increment is important!
```

### Wrong (Infinite Loop)
```python
i = 1

while i < 6:
    print(i)
    # Missing i += 1 - Loop runs forever!
```

---

## While Loop Requirements

Before using a while loop, you need:

| Requirement | Description | Example |
|-------------|-------------|---------|
| Variable | Define loop variable | `i = 1` |
| Condition | Set loop condition | `while i < 6` |
| Increment | Update variable | `i += 1` |

---

## The Break Statement

**Definition:** The break statement stops the loop even if the condition is still true.

### Syntax
```python
while condition:
    if break_condition:
        break
    statement
```

### Example
```python
i = 1

while i < 6:
    print(i)
    if i == 3:
        break
    i += 1

# Output:
# 1
# 2
# 3
```

**Note:** Loop stops at 3, even though condition says i < 6.

---

## The Continue Statement

**Definition:** The continue statement stops the current iteration and continues with the next iteration.

### Syntax
```python
while condition:
    if continue_condition:
        continue
    statement
```

### Example
```python
i = 0

while i < 6:
    i += 1
    if i == 3:
        continue
    print(i)

# Output:
# 1
# 2
# 4
# 5
# 6
```

**Note:** Number 3 is skipped because of continue.

---

## Break vs Continue

| Statement | Action | Loop Continues? |
|-----------|--------|-----------------|
| `break` | Exit loop completely | No |
| `continue` | Skip current iteration | Yes |

### Visual Comparison

```python
# Break - stops at 3
i = 1
while i < 6:
    print(i)
    if i == 3:
        break
    i += 1
# Output: 1, 2, 3

# Continue - skips 3
i = 0
while i < 6:
    i += 1
    if i == 3:
        continue
    print(i)
# Output: 1, 2, 4, 5, 6
```

---

## The Else Statement

**Definition:** The else block executes once when the loop condition becomes false.

### Syntax
```python
while condition:
    statement
else:
    final_statement
```

### Example
```python
i = 1

while i < 6:
    print(i)
    i += 1
else:
    print("i is no longer less than 6")

# Output:
# 1
# 2
# 3
# 4
# 5
# i is no longer less than 6
```

---

## Else with Break

**Important:** The else block will NOT execute if the loop is stopped by a break statement.

### Example: Else Executes
```python
i = 1

while i < 4:
    print(i)
    i += 1
else:
    print("Loop completed normally")

# Output:
# 1
# 2
# 3
# Loop completed normally
```

### Example: Else Does NOT Execute
```python
i = 1

while i < 6:
    print(i)
    if i == 3:
        break
    i += 1
else:
    print("This will not print")

# Output:
# 1
# 2
# 3
```

---

## Practical Examples

### Example 1: Countdown
```python
count = 5

while count > 0:
    print(count)
    count -= 1

print("Blast off!")

# Output:
# 5
# 4
# 3
# 2
# 1
# Blast off!
```

### Example 2: Sum of Numbers
```python
total = 0
number = 1

while number <= 5:
    total += number
    number += 1

print(f"Sum: {total}")

# Output: Sum: 15
```

### Example 3: User Input Validation
```python
password = ""

while password != "python123":
    password = input("Enter password: ")
    if password != "python123":
        print("Wrong password, try again")

print("Access granted!")
```

### Example 4: Find First Multiple
```python
number = 1

while True:
    if number % 7 == 0:
        print(f"First multiple of 7: {number}")
        break
    number += 1

# Output: First multiple of 7: 7
```

### Example 5: Skip Even Numbers
```python
i = 0

while i < 10:
    i += 1
    if i % 2 == 0:
        continue
    print(i)

# Output: 1, 3, 5, 7, 9
```

---

## Nested While Loops

**Definition:** A while loop inside another while loop.

### Example
```python
i = 1

while i <= 3:
    j = 1
    while j <= 3:
        print(f"i={i}, j={j}")
        j += 1
    i += 1

# Output:
# i=1, j=1
# i=1, j=2
# i=1, j=3
# i=2, j=1
# i=2, j=2
# i=2, j=3
# i=3, j=1
# i=3, j=2
# i=3, j=3
```

---

## Common While Loop Patterns

### Pattern 1: Count Up
```python
i = 1
while i <= 5:
    print(i)
    i += 1
```

### Pattern 2: Count Down
```python
i = 5
while i > 0:
    print(i)
    i -= 1
```

### Pattern 3: Infinite Loop with Break
```python
while True:
    user_input = input("Enter 'quit' to exit: ")
    if user_input == "quit":
        break
```

### Pattern 4: Condition-Based
```python
balance = 100
while balance > 0:
    withdrawal = 20
    balance -= withdrawal
    print(f"Balance: {balance}")
```

---

## While Loop Control Flow

| Statement | Purpose | Example |
|-----------|---------|---------|
| `while` | Start loop | `while i < 10:` |
| `break` | Exit loop | `if i == 5: break` |
| `continue` | Skip iteration | `if i == 3: continue` |
| `else` | After loop ends | `else: print("Done")` |

---

## Common Mistakes

### Mistake 1: Forgetting to Increment
```python
# Wrong - Infinite loop
i = 1
while i < 5:
    print(i)
    # Missing: i += 1

# Correct
i = 1
while i < 5:
    print(i)
    i += 1
```

### Mistake 2: Wrong Increment Position with Continue
```python
# Wrong - Infinite loop if i == 3
i = 0
while i < 5:
    if i == 3:
        continue
    print(i)
    i += 1  # Never reached when i == 3

# Correct
i = 0
while i < 5:
    i += 1  # Increment first
    if i == 3:
        continue
    print(i)
```

### Mistake 3: Condition Never Becomes False
```python
# Wrong
i = 1
while i > 0:  # Always true
    print(i)
    i += 1  # Makes i larger, never <= 0

# Correct
i = 1
while i < 5:  # Will become false
    print(i)
    i += 1
```

---

## When to Use While Loop

| Use While Loop When | Use For Loop When |
|---------------------|-------------------|
| Unknown iterations | Known iterations |
| Condition-based | Iterating sequence |
| User input loops | Fixed range |
| Infinite loops | Collection iteration |

---

## Quick Reference

### Basic While Loop
```python
i = 1
while i < 6:
    print(i)
    i += 1
```

### With Break
```python
while condition:
    if break_condition:
        break
```

### With Continue
```python
while condition:
    if continue_condition:
        continue
```

### With Else
```python
while condition:
    statement
else:
    final_statement
```

### Infinite Loop
```python
while True:
    if exit_condition:
        break
```

---

## Key Takeaways

### ✅ Remember
- **While loop** repeats while condition is True
- **Always increment** loop variable to avoid infinite loops
- **break** exits the loop completely
- **continue** skips current iteration, continues loop
- **else** executes when loop ends normally (not with break)
- **Increment before continue** to avoid infinite loops
- **while True** creates infinite loop (use with break)

### 🎯 Interview Important
- Difference between break and continue
- When else block executes (not with break)
- How to avoid infinite loops
- While vs for loop usage
- Nested while loops execution order
- Common while loop patterns

---

**Master while loops to handle condition-based repetition in your programs!**
