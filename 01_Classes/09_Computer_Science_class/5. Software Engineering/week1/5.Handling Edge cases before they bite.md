---
type: lecture
class: "[[Software Engineering]]"
tags:
  - SE
  - Python
  - Edge_cases
  - Guards
  - if,elif,else
  - Functions
  - lecture
  - 2026-04-13
date: 2026-04-13 20:49
topics: [Edge_cases, Python, Software_Engineering,Computer_Science, Crashes, Unexpected_inputs]
---
# Handling Edge cases before they bite

## 📌 Overview
*   **Course:** Using Guards to protect code from unexpected inputs and system crashes
*   **Lecture Date:** 
*   **Instructor:** 

## 🎯 Learning Objectives
*   Use a function for a single job and call outside the function with a printed message do not combine them into a messy code block
* Use clear concise code
* Call outside with printed messages

## 📝 Notes
*   Use guards to protect functions from improper inputs so script or programs dont crash from unexpected  inputs or outputs or Both
* if, elif, and else clause at the beggining of your function to protect code example below
* **1. What’s an edge case?**

> An **edge case** is an input that is unusual, extreme, or “wrong” for your function — and likely to break it or make it behave weirdly.

Two big kinds you used:

- **Type edge cases** – wrong _kind_ of value
    - Examples: `"10"`, `""`, `None` when you expect a number
- **Value edge cases** – wrong _value_, even if type is right
    - Examples: `b == 0` in division, negative ages, super large numbers

**2. Guard clauses / early return**  
You used this pattern:

Python

```python
def safe_divide(a, b):
    # guards (checks first)
    if ...bad input...:
        return None

    # happy path
    return a / b
```

Key ideas:

- Guards go at the **top** of the function.
- If input is bad → **return early**.
- Only if all guards pass → run the “real” logic.

This is called a **guard clause**.

**3. Your final `safe_divide` pattern**

Python

```python
def safe_divide(a, b):
    # type guards
    if type(a) is not int and type(a) is not float:
        return None
    elif type(b) is not int and type(b) is not float:
        return None
    # value guard
    elif b == 0:
        return None
    else:
        return a / b
```

It protects against:

- non-number `a`
- non-number `b`
- `b == 0` (division by zero)

And returns the real result only when input is safe ✅

## 💻 Code Examples / Algorithms

Edge Cases guards against improper inputs:

```python
def safe_divide(a, b):
    if type(a) is not int and type(a) is not float:
        return None
    elif type(b) is not int and type(b) is not float:
        return None
    elif b == 0:
        return None
    else:
        total = a / b
        return total

print(safe_divide(1, 2))
print(safe_divide('a',2))
print(safe_divide(1,'b'))
print(safe_divide(1, 0))
```

