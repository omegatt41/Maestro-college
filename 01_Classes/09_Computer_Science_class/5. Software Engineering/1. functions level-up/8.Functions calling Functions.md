---
type: lecture
class: "[[Software Engineering]]"
tags:
  - SE
  - lecture
  - Functions
  - Python
  - 
  - 2026-04-14
date: 2026-04-14 21:33
topics: [Functions, Calling-Functions]
---
# Functions calling Functions

## 📌 Overview
*   **Course:** Piplines in programs using main()
*   **Lecture Date:** 2026-04-14 
*   **Instructor:** maestro

## 🎯 Learning Objectives
*   using main() to pipeline your code

## 📝 Notes
*   DONOT FORGET to use variables inside main when calling functions to use with the nxt function

## 💻 Code Examples / Algorithms

**1. Pipeline idea**

> A **pipeline** is when the **output** of one function becomes the **input** of the next.

Example:

```python
def add_ten(x):
    return x + 10

def double(x):
    return x * 2

def main():
    number = 50
    step1 = add_ten(number)   # 60
    step2 = double(step1)     # 120
    return step2
```

Flow: `50 → add_ten → 60 → double → 120`

---

**2. Single-responsibility functions**

Each function should do **one clear job**:

```python
def c_to_f(c):
    return c * 9/5 + 32   # only conversion

def add_five(x):
    return x + 5          # only add 5
```

This makes them easy to **reuse** and **chain**.

---

**3. `return` vs `print` in pipelines**

- Use **`return`** inside your functions so other functions can use the value.
- Use **`print()`** only at the **end** (usually in `main()`), to show the final result.

Bad (hard to reuse):

```python
def add_ten(x):
    print(x + 10)   # prints, but doesn't give a value back
```

Good (pipeline-friendly):

```python
def add_ten(x):
    return x + 10
```

---

**4. How to trace a pipeline**

To predict what a program prints:

1. Start with the initial value
2. Apply the first function → write the result
3. Feed that into the next function
4. Keep going until the `return` from `main()`
5. Whatever `main()` returns is what `print(main())` shows

You did this with:

- temperatures (`c_to_f` → `add_five`)
- money and numbers
- calories (`add_snack` → `subtract_workout`)

