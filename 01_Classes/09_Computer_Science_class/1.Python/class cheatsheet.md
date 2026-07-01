---
type: lecture
class: "[[class cheatsheet]]"
tags:
  - class/oop
date: 2026-06-30 20:21
topics: []
cssclasses:
---

# OOP Cheat Sheet: Multiple Objects from One Class (Python)

# 1. Define a minimal class
class Car:
    pass

# 2. Create multiple objects (instances)
car1 = Car()
car2 = Car()
car3 = Car()

# 3. Give each object its own attributes
car1.color = "red"
car1.speed = 120

car2.color = "blue"
car2.speed = 90

car3.color = "green"
car3.speed = 190

# 4. Each object keeps its own state
# Changing car1 does NOT change car2 or car3
car1.color = "black"

print(car1.color, car1.speed)  # black 120
print(car2.color, car2.speed)  # blue 90
print(car3.color, car3.speed)  # green 190

# 5. Key ideas (summary)
 - One class → many objects
- Each object has independent attributes (its own copy of data)
# - Variable name vs attributes:
	- car1  = variable (label)
	- car1.color / car1.speed = data stored inside that object