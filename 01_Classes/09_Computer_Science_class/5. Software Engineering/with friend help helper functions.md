---
type: lecture
class: "[[Software Engineering]]"
tags:
  - SE
  - lecture
  - 2026-04-15
date: 2026-04-15 22:06
topics: []
---
# with friend help helper functions

## 📌 Overview
*   **Course:** helper function
*   **Lecture Date:** 2026-04-15 
*   **Instructor:** maestro

## 🎯 Learning Objectives
*   write code
*   clean it up with helper functions
	* one job per function
*  test code make sure it still work
	* impliment guards to prevent crashes or courruption of code

## 📝 Notes
*   **1. What a helper function is**

- A **helper function** is a small, single-purpose function you create to:
    - Remove duplicated code, or
    - Hide a chunk of complexity behind a clear name.
- It usually comes **after** you already have working code.


Job: given a `price` and `tax_rate`, return the total with tax. Nothing else.

**2. Make it work → then make it clean**

Two-phase habit:

1. **Make it work**
    
    - Write code that’s maybe messy or duplicated.
    - Confirm behavior/output is correct.
2. **Make it clean**
    
    - Extract helpers for repeated or complex logic.
    - Replace old blocks with calls to the new helpers.
    - Verify output is **unchanged**.

Key rule: refactoring **does not change behavior**, only structure.

**3. Removing duplicated logic with helpers**



Now the tax logic exists in **one** place.

**4. Helpers should return, not print**

- Helpers **compute** and `return` a value.
- The “main” part of your script decides **if/how to print**.


**5. Formatting as a separate responsibility**

- **`calculate_total`** = math
- **`format_receipt_line` / `format_total`** = string formatting
- Main flow = orchestration (calls helpers + prints)

**6. The “boss” vs helpers**

- The code at the bottom (often `main()` or top-level script) is the **boss**:
    - Knows the overall steps.
    - Calls helpers in the right order.
- Helpers are **workers**:
    - Each knows one narrow job and does it well.

Your final custom program nailed this pattern:

- `calculate_total(price)`
- `format_total(total)`
- `main()` calling them.

## 💻 Code Examples / Algorithms
Example:
Original duplication (pizza example):

Python

```python
tax_rate = 0.08

price1 = 10.0
tax1 = price1 * tax_rate
total1 = price1 + tax1

price2 = 15.0
tax2 = price2 * tax_rate
total2 = price2 + tax2
```

Refactored with helper:

Python

```python
def calculate_total(price, tax_rate):
    tax = price * tax_rate
    total = price + tax
    return total

tax_rate = 0.08
price1 = 10.0
price2 = 15.0

total1 = calculate_total(price1, tax_rate)
total2 = calculate_total(price2, tax_rate)
```


Python

```python
def calculate_total(price, tax_rate):
    tax = price * tax_rate
    total = price + tax
    return total
```


Second helper: formatting output.

Python

```python
def format_receipt_line(label, amount):
    line = f"{label}: ${amount:.2f}"
    return line
```

Bad helper (mixes concerns):

Python

```python
def calculate_total(price, tax_rate):
    total = price + price * tax_rate
    print(total)   # ❌ side effect
```

Better:

Python

```python
def calculate_total(price, tax_rate):
    total = price + price * tax_rate
    return total   # ✅ pure calculation
```

Usage:

Python

```python
total1 = calculate_total(price1, tax_rate)
line1 = format_receipt_line("First pizza", total1)
print(line1)
```
