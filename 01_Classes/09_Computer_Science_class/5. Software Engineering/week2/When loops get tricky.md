---
type: lecture
class: "[[Software Engineering]]"
tags:
  - SE
  - loops
  - lecture
  - 2026-04-21
date: 2026-04-21 20:46
topics: [loops]
---
# When loops get tricky

## 📌 Overview
*   **Course:** Software Engineering
*   **Lecture Date:** 2026-04-21 
*   **Instructor:** maestro

## 🎯 Learning Objectives
* flags is a bool response it starts false and flips True
	*  A True/False variable that remembers if something has happened during the loop
* break = stop the whole loop immediately , not just skip one step 
## 📝 Notes
*   **1. Accumulators (running totals / counts)**

- Pattern:
    
    ```python
    total = 0
    for x in items:
        total += x
    ```
    
- You used this correctly several times.
- Watch out: whether you add **before or after** a condition can change the result.

---

**2. Boolean flags (True/False switches)**

- Pattern:
    
    ```python
    found_error = False
    
    for msg in messages:
        if "ERROR" in msg:
            found_error = True
    ```
    
- A flag **remembers** if something happened during the loop.
- You used flags to track:
    - if a big number was found
    - if an error was seen in messages

---

**3. Early exit with `break`**

- Pattern:
    
    ```python
    for item in items:
        if condition:
            # maybe set a flag
            break
    ```
    
- `break` stops the **entire loop immediately**, not just that iteration.
- You used `break` to:
    - stop scanning messages once `"ERROR"` appeared
    - stop adding numbers once the running total passed a limit

---

**4. Order of lines inside the loop matters**  
These two are **not** the same:

```python
if num > 8:
    break
total += num
```

vs

```python
total += num
if num > 8:
    break
```

You saw that:

- In the first: the triggering value is **not** added
- In the second: the triggering value **is** added

You handled this difference well once we called it out.

---

**5. Tracing to avoid off-by-one bugs**

- Adding `print(msg)` or `print(total)` _inside_ the loop helps you see:
    - how many iterations actually ran
    - where `break` fired
- You used this to see exactly which messages were processed before stopping.

---

If you want to be extra sharp, you can quickly review your mental checklist next time you write a loop:

- Do I need a **running total / count**? → accumulator
- Do I just need to remember if something happened? → flag
- Can/should I **stop early**? → `break`
- Is the **order** of my `if`, `break`, and `+=` lines correct?

