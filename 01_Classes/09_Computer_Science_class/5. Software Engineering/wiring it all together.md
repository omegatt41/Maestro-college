---
type: lecture
class: "[[Software Engineering]]"
tags:
  - SE
  - lecture
  - 2026-04-16
date: 2026-04-16 17:27
topics: []
---
# wiring it all together

## 📌 Overview
*   **Course:** 
*   **Lecture Date:** 2026-04-16 
*   **Instructor:** 

## 🎯 Learning Objectives
*   Build a working simple program to covert temp to celsius and add an offset such as the

## 📝 Notes
*   **Program structure (pattern to reuse):**

1. **Helpers** (pure logic, no printing)
    
    - One clear job each
    - Take input through parameters
    - Return a result with `return`
    
    From your code:
    
    ```python
    def fahrenheit_to_celsius(fahrenheit):
        celsius = (fahrenheit - 32) * 5/9
        return celsius
    
    def add_celsius_offset(celsius, offset):
        corrected_temp = celsius + offset
        return corrected_temp
    ```
    
2. **`main()` function** (orchestrator)
    
    - Creates starting data
    - Calls helpers in order
    - Handles **all printing**
    
    Your `main()`:
    
    ```python
    def main():
        fahrenheit = 77
        offset = 2
        celsius_conversion = fahrenheit_to_celsius(fahrenheit)
        offset_temp = add_celsius_offset(celsius_conversion, offset)
        print(f"The corrected converted temp from fahrenheit to celcius plus offset is: {offset_temp}")
    ```
    
3. **Entry-point guard** (controls when `main()` runs)
    
    ```python
    if __name__ == "__main__":
        main()
    ```
    
    - When you **run the file directly**, this condition is `True` → `main()` runs.
    - When you **import the file as a module**, this condition is `False` → `main()` does _not_ run automatically.

**Mental model to reuse in other programs:**

- Think: **Input → helper → helper → output**, with `main()` coordinating.
- Rule: **Helpers don’t print**; they _return_.
- Rule: **Names tell the story** (`fahrenheit_to_celsius`, `add_celsius_offset`, not vague names).

# Script Template:

# 1) Helper functions (pure logic, no printing)

def first_helper(input_value):
    """
    Does one clear thing with input_value.
    Returns the result.
    """
    # TODO: replace this with real logic
    result = input_value  # placeholder
    return result


def second_helper(some_value, extra_value):
    """
    Does one clear thing using some_value and extra_value.
    Returns the result.
    """
    # TODO: replace this with real logic
    combined = some_value  # placeholder
    return combined


# 2) main() orchestrates everything
```python
def main():
    # Step 1: set up starting data (input)
    start_value = 0  # TODO: change this

    # Step 2: call first helper
    first_result = first_helper(start_value)

    # Step 3: call second helper
    second_result = second_helper(first_result, 0)  # TODO: change second arg

    # Step 4: print final output
    print("Final result:", second_result)


# 3) Entry point guard

if __name__ == "__main__":
    main()
```
