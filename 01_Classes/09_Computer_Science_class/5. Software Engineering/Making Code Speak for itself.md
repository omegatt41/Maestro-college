---
type: lecture
class: "[[Software Engineering]]"
tags:
  - SE
  - lecture
  - 2026-04-13
date: 2026-04-13 21:29
topics: []
---
# Making Code Speak for itself

## 📌 Overview
*   **Course:** Making Code speak for itself
*   **Lecture Date:** 04/13/2026 
*   **Instructor:** Maestro College

## 🎯 Learning Objectives
*   Make code easier to read using docstrings and comments so whoever is reading it can identify all parts of the code clearly
* use short clear names for functions and variables

## 📝 Notes
*   **1. Naming functions and parameters (Python style)**

- Use **snake_case**: all lowercase with `_` between words.
    - ✅ `add_tax`, `before_tax_price`
    - ❌ `addTax`, `Extra_charges`
- Use **verbs** for functions that _do_ something.
    - `calculate_total`, `format_name`, `send_email`
- Use **clear nouns** for parameters that describe _what_ the value is.
    - `before_tax_price`, `extra_charges`, `tax_rate`
- Good test: **read it aloud**.
    - “Call `add_tax` with `before_tax_price` and `extra_charges`”  
        If that sounds like a sentence that explains itself, the names are good.

**2. Docstrings (function documentation)**

A **docstring** is:

> A triple-quoted string right under `def` that explains what the function does.

Basic template:

Python

```python
def add_tax(before_tax_price, extra_charges):
    """Short summary of what the function does.

    Args:
        before_tax_price: What this value represents.
        extra_charges: What this value represents.

    Returns:
        What the function gives back.
    """
    # function body here
```

Key points:

- First line: **one short sentence** describing the function’s main job.
- Blank line, then optional sections like **Args** and **Returns**.
- Docstring must be the **very first thing** inside the function.
- Make sure **docstring matches the code** (no lies about what it returns).

**3. Inline comments (the right way)**

Inline comments are for explaining **why**, not **what**:

- Use `#` for comments:
    
    ```python
    # Use fixed 8.25% sales tax rate
    tax_amount = before_tax_price * 0.0825
    ```
    
- Don’t comment obvious things:
    
    ```python
    total = a + b  # add a and b   # ❌ pointless
    ```
    
- Best uses:
    - Magic numbers or special constants (`0.0825` tax rate)
    - Non-obvious business rules
    - Tricky formulas or workarounds


This shows all three ideas working together:

- Clear names
- Docstring
- Inline comments with purpose

## 💻 Code Examples / Algorithms

**4. Your final function (as a clean reference)**

Python final version with docstrings and comments to explain code

```python
def add_tax(before_tax_price, extra_charges):
    """Calculate total_with_tax plus any additional charges.

    Args:
        before_tax_price: Price before tax is applied.
        extra_charges: Additional fees to add to the total.
        
    Returns:
        Total including tax and extra charges.
    """
    tax_amount = before_tax_price * 0.0825  # calculating tax_amount using 0.0825 % tax
    total_with_tax = before_tax_price + tax_amount  # base price + tax_amount
    return total_with_tax + extra_charges  # total_with_tax + extra charges
```
