---
type: lecture
class: "[[Software Engineering]]"
tags:
  - Software_engineering
  - Refactoring_Code
  - SE
  - lecture
  - 2026-04-13
date: 2026-04-13 20:24
topics: [Functions,Python,Software_Engineering]
---
# One Job per Function
		1. Clear concise job
		2. use a simple function for calculations
		3. call it outside the function with a printed message

## 📌 Overview
*   **Course:** Software-Engineering
*   **Lecture Date:**  
*   **Instructor:** Maestro

## 🎯 Learning Objectives
*   **Single-responsibility principle** = one function should have one clear reason to change / one main job.
	* If you describe it with “and” (like “calculate total _and_ print bill”), that’s a warning sign 🚨
*  

## 📝 Notes
*   **1. Keep the “math” clean and separate**

- Put **calculations** in their own function.
- That function should usually just:
    - take inputs (parameters)
    - do the math
    - `return` the result
- No prints inside if possible.



---



This way:

- helper = **one job** (calculate)
- main code = **talks to the user**

---

**3. Quick self-check when you write a function**

Ask yourself:

- Do I need the word **“and”** to describe it?
    - “Calculate total **and** print the bill” → doing too much.
- Does it both **compute** and **print**?
    - Split them.
- Could I reuse this function in another program?
    - If it’s pure (just returns a value), it’s much easier.

## 💻 Code Examples / Algorithms
Example:
**1. Use a single job in a function to do the calculations
```python
def calculate_total_with_tip(total):
    tip_percent = 0.06
    tip_amount = total * tip_percent
    final_total = total + tip_amount
    return final_total
```

**2. Handle messages outside the helper**

Use the returned value to print or show messages:

```python
total = calculate_total_with_tip(5)
print("Your total with tip is:", total)
print("Thank you for visiting our restaurant!")
```

Function Template:

```python
def my_calculation(input_value):
    # 1. Do your math / logic using input_value
    result = input_value  # change this to your real calculation

    # 2. Return the result (no prints here)
    return result
```

And then you use it **outside** like this:

Python

```python
value = my_calculation(10)
print("Result is:", value)
```

Here’s a more concrete version you can adapt:

Python

```python
def calculate_something(x):
    # do calculations
    step1 = x * 2
    step2 = step1 + 3
    final_result = step2
    return final_result

result = calculate_something(5)
print("The final result is:", result)
```

Pattern to remember:

1. **Function:** get inputs → compute → `return`
2. **Outside:** call function → `print` or show messages