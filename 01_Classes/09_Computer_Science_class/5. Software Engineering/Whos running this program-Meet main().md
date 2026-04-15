---
type: lecture
class: "[[Software Engineering]]"
tags:
  - SE
  - lecture
  - 2026-04-14
date: 2026-04-14 21:18
topics: []
---
# Whos running this program-Meet main()

## 📌 Overview
*   **Course:** main()
*   **Lecture Date:** 2026-04-14 
*   **Instructor:** maestro

## 🎯 Learning Objectives
*   use main() to define the order of the program to run functions and put guard at the bottom “if __name__ = “__main__”: main()” that way the ordered program function to define the order the other functions in the program run in
* if you import the app.py from another app __name__ will not be __main__ so the ordered function of main() will not run it safeguards it so you can call the app from another app without running the whole thing to be able to use the functions within
* __main__ is a traffic controller

## 📝 Notes
*   

## 💻 Code Examples / Algorithms
```python

if __name__ == "__main__":
    main()
```

template of a python program with guard:
```python

# 1) Imports (if any)
import something

# 2) Helper functions
def do_something():
    print("Doing something...")


# 3) main() – the traffic controller
def main():
    # Call your helper functions here in order
    do_something()


# 4) Entry point guard
if __name__ == "__main__":
    main()
```
Quick mental checklist:

1. **Top:** imports (if needed)
2. **Middle:** helper functions with clear names
3. **Then:** `main()` that _orchestrates_ what happens
4. **Bottom:** `if __name__ == "__main__":` calling `main()`
