---
type: lecture
class: "[[Software Engineering]]"
tags:
  - SE
  - lecture
  - 2026-04-13
date: 2026-04-13 18:41
topics: [Software_Engineering, Computer_Science]
---
# Why Does this script feel wrong

## 📌 Overview
*   **Course:** Software Engineering
*   **Lecture Date:** 
*   **Instructor:** 

## 🎯 Learning Objectives
*   A script can work but be functionaly hard to follow and messy to read
* simplify code as much as possible and use clear variable names

## 📝 Notes
*   **Key “code smells” you saw**

1. **Copy‑paste repetition**
    
    - Same logic or numbers written in many places.
    - Example: medium coffee price `4` appears in multiple `if` blocks and in tax calculations.
    - Risk: when the price changes, you must update it in several spots; missing one creates silent bugs.
2. **Tangled / “spaghetti” flow**
    
    - Many `if/elif/else` blocks scattered around the script.
    - Hard to trace what actually happens for one case (e.g., “medium, happy hour, member”).
    - You end up jumping around the file to understand a single path.
3. **Messy, repetitive variable patterns**
    
    - Variables like `c1_price`, `c2_price`, `c3_price` that repeat the same idea with just a number.
    - They “work”, but make the code harder to read and maintain.

**Why this matters (maintainability vs. just correctness)**

- **Correctness**: “Does it give the right answer right now?”
- **Maintainability**: “How easy and safe is it to change later?”

Copy‑paste and tangled flow hurt maintainability because:

- Any change (prices, tax, discounts, new drink) means editing **many places**.
- It’s easy to miss one place and create **hidden inconsistencies**.
- New features make the “wall of code” worse over time.

You learned to say things like:

> “It works, but changing the price means editing several places — that’s risky.”

**Modular thinking (without writing functions yet)**

You started thinking in a modular way:

- “This pattern (ask → decide price → tax → print) is repeated 3 times.”
- “This could be **one chunk** reused, not three separate copies.”

That mindset is the bridge to **functions**:

- Take a repeated pattern.
- Give it one clear place to live and a clear name.
- Reuse it instead of copy‑pasting.

(The next lesson is where you actually do this with `def`.)

## 💻 Code Examples / Algorithms
```<% tp.file.cursor() %>

