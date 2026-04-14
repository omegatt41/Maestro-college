---
type: lecture
class: "[[Software Engineering]]"
tags:
  - Python
  - Software_engineering
  - Refactoring_Code
  - SE
  - lecture
  - 2026-04-13
date: 2026-04-13 18:54
topics: [refactoring code, Software_Engineering,Python,Computer_Science]
---
# Inputs, outputs and the return contract

## 📌 Overview
*   **Course:** Inputs, Outputs and the return contract
*   **Lecture Date:** 
*   **Instructor:** Maestro

## 🎯 Learning Objectives
* How to refactor code into reusable smaller scripts for a cleaner look and readability.
* Use functions instead of single line codes to minimize code usage

## 📝 Notes
*   **1. Input → Output boundary**

Think of a chunk of code and ask:

> “What goes _in_? What should come _out_?”

Example from the tax script:

Python

```python
tax_rate = 0.08

price = 50
tax_amount = price * tax_rate
total_price = price + tax_amount
print(total_price)
```

- **Input**: `price`
- **Output**: `total_price` (price with tax)
- The _boundary_ for the function is the part that transforms `price` into `total_price`.

So we move this logic into a function and leave `price = ...` and `print(...)` outside.

**2. Return contract**

A **return contract** is the promise your function makes:

> “Given X as input, I will _return_ Y.”

For your function:

Python

```python
def add_tax(price):
    tax_amount = price * tax_rate
    total_price = price + tax_amount
    return total_price
```

- Contract:
    - **Input**: `price` (number)
    - **Output**: total price including tax (number)

You then decide what to _do_ with that result outside:

Python

```python
print(add_tax(50))
print(add_tax(120))
```

**3. `return` vs `print`**

- **`return`**
    
    - Sends a value _back_ to the caller.
    - Lets you store it, reuse it, do more math, pass it to other functions.
    - Ends the function immediately.
- **`print`**
    
    - Just shows text on the screen.
    - The function’s result is effectively `None` (if you don’t explicitly return).
    - You _can’t_ do more math with something that was only printed.

Example:

Python

```python
# Good: composable
total_cheap = add_tax(50)
total_expensive = add_tax(120)
difference = total_expensive - total_cheap
print(difference)
```

This works **because** `add_tax` uses `return`, not `print`.

If `add_tax` only printed and didn’t return, both `total_cheap` and `total_expensive` would be `None`, and the math would fail.

**4. Simple extraction pattern**

When you see duplicated logic:

1. Identify the **input** (what changes).
2. Identify the **output** (the final value you care about).
3. Move the transforming code into a function.
4. Make the function:
    - accept the input as a parameter
    - compute the result
    - **return** the result
5. Replace duplicated blocks with function calls.


```

## 💻 Code Examples / Algorithms
```<% tp.file.cursor() %>
```

start with:
	
```python
tax_rate = 0.08

price = 50
tax_amount = price * tax_rate
total_price = price + tax_amount
print(total_price)
```

turns into reusable code easier to read:

```python
Your final refactor:

Python


tax_rate = 0.08

def add_tax(price):
    tax_amount = price * tax_rate
    total_price = price + tax_amount
    return total_price

print(add_tax(50))
print(add_tax(120))