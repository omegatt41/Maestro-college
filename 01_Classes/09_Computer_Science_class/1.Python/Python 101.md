**  
python 101 detailed review notes**

---

**1. basic concepts**

- Python files end with `.py`.
- Indentation (4 spaces or a tab) defines code blocks — no `{}`.
- Comments use `#` for single-line, triple quotes (`"""`) for docstrings or multi-line comment blocks.

---

**2. variables and data types**

- Variables are created on assignment, names must start with a letter or `_`.
- No need to declare the type beforehand.
- Common data types:
    - `int`: Whole numbers, e.g. `age = 24`
    - `float`: Decimal numbers, e.g. `height = 1.75`
    - `str`: Text, e.g. `name = "Tylor"`
    - `bool`: `True` or `False`
- Type conversion: `int("2")`, `str(5)`, `float("2.9")`
- Use `type(var)` to check the type.

---

**3. input and output**

- Output: `print()`, supports multiple arguments, separated by commas.
    - Example: `print("Age:", age)`
- Input: `input()` always returns a string.
    - Example: `age = int(input("Enter your age: "))`

---

**4. operators**

- Arithmetic: `+`, `-`, `*`, `/` (divides, returns float), `//` (floor division), `%` (remainder), `**` (power).
- Assignment: `=`, `+=`, `-=`, etc.
- Comparison: `==` (equals), `!=` (not equal), `>`, `<`, `>=`, `<=`
- Logical: `and`, `or`, `not`
- Membership: `in`, `not in` (for strings, lists, etc.)

---

**5. conditionals**

- Use `if`, `elif`, and `else` to branch logic.
    
    ```python
    if score >= 90:
        print("A")
    elif score >= 80:
        print("B")
    else:
        print("C or less")
    ```
    
- Boolean expressions are used for conditions.
- Indentation is required for the block under each branch.

---

**6. loops**

- **while loops**:
    
    - Repeats as long as its condition is `True`.
    - Example:
        
        ```python
        x = 0
        while x < 5:
            print(x)
            x += 1
        ```
        
    - Infinite loop: `while True: ...`, stop with `break`.
- **for loops**:
    
    - Used for iterating over a sequence (list, string, range).
    - Example:
        
        ```python
        for char in "hello":
            print(char)
        ```
        
        ```python
        for i in range(3):  # 0, 1, 2
            print(i)
        ```
        
    - `range(start, stop, step)`
    - `break` exits the loop early.
    - `continue` skips to the next iteration.

---

**7. functions**

- Define using `def`:
    
    ```python
    def say_hello(name):
        print("Hello " + name)
    ```
    
- Can have default arguments:
    
    ```python
    def greet(name, msg="Hi"):
        print(msg, name)
    ```
    
- Return with `return`:
    
    ```python
    def add(a, b):
        return a + b
    result = add(2, 3)
    ```
    
- Arguments can be positional or keyword (`greet(name="Joe", msg="Hey")`).
- Scope: Variables created inside a function are local unless declared `global`.

---

**8. lists and tuples**

- **Lists**:
    
    - `nums = [10, 20, 30]`
    - Change elements: `nums[1] = 25`
    - Slicing: `nums[1:3]` returns `[20, 30]`
    - List methods:
        - `append(4)`, `insert(1, 15)`, `remove(20)`, `pop()`, `sort()`, `reverse()`, `index(10)`, `count(10)`
    - Nested lists: `matrix = [[1,2,3],[4,5,6]]`
- **Tuples**:
    
    - Like lists, but immutable (`my_tuple = (5, 6, 7)`)
    - Useful for fixed collections, can be used as dictionary keys

---

**9. dictionaries**

- Key-value pairs:
    
    - `student = {"name": "Tylor", "age": 20}`
    - Access value: `student["name"]`
    - Set value: `student["age"] = 21`
    - Add key: `student["major"] = "CS"`
    - Remove key: `del student["major"]`
    - Keys must be unique and immutable (strings, numbers, tuples).
- Dictionary methods:
    
    - `.get("key", default)`, `.keys()`, `.values()`, `.items()`

---

**10. strings**

- Strings are immutable.
- Concatenate: `full = first + " " + last`
- f-strings: `f"{name} is {age} years old."`
- Escape: `\n` (newline), `\t` (tab), `\'`, `\"`
- String methods: `.upper()`, `.lower()`, `.title()`, `.strip()`, `.split(",")`, `.replace("a", "b")`, `.find("a")`

---

**11. importing modules**

- Python has built-in modules for extra functionality:
    - `import math`, `import random`
    - Use with dot notation: `math.sqrt(9)`, `random.randint(1,10)`
    - `from datetime import date`
- Install third-party packages with pip (not in the review, but good to know).

---

**12. error handling**

- Use `try`/`except`:
    
    ```python
    try:
        result = num / denom
    except ZeroDivisionError:
        print("Cannot divide by zero!")
    except Exception as e:
        print("Other error:", e)
    ```
    
- `finally:` block always runs.

---

**13. working with files (basics)**

- Write:
    
    ```python
    with open("myfile.txt", "w") as f:
        f.write("Hello\nWorld")
    ```
    
- Read:
    
    ```python
    with open("myfile.txt", "r") as f:
        content = f.read()
    ```
    

---

**14. common built-in functions**

- `print()`, `input()`
- `type()`, `len()`, `str()`, `int()`, `float()`, `list()`, `dict()`, `sum()`, `min()`, `max()`
- `range()`, `enumerate()`, `zip()`

---

If you want examples for any concept or want these organized by week or topic, just say the word!  
Good luck making your notes!

correction how about a complete python cheatsheet

Great idea! Here’s a **Python 101 cheatsheet** with core syntax, commands, and concepts—all in one spot.

---

**python 101 cheatsheet**

---

**basic syntax**

```python
# single line comment

"""multi-line
comment or docstring"""

# variables
x = 10
name = "Tylor"
is_active = True
```

---

**data types**

- Integer: `x = 5`
- Float: `y = 3.14`
- String: `s = "hi"`
- Boolean: `done = False`
- List: `lst = [1, 2, 3]`
- Tuple: `tup = (4, 5, 6)`
- Dictionary: `d = {"a": 1, "b": 2}`

---

**input/output**

```python
print("Hello,", name)
age = input("Enter your age: ")        # always string
age = int(age)                         # convert to int
```

---

**operators**

- Arithmetic: `+`, `-`, `*`, `/`, `//`, `%`, `**`
- Comparison: `==`, `!=`, `>`, `<`, `>=`, `<=`
- Logical: `and`, `or`, `not`
- Membership: `in`, `not in`
- Assignment: `=`, `+=`, `-=`, etc.

---

**strings**

```python
msg = "hello"
msg.upper()         # 'HELLO'
msg.lower()         # 'hello'
msg.title()         # 'Hello'
msg.strip()         # remove spaces
msg.replace("e", "a")
msg.find("o")
"l" in msg          # True
f"Hi, {name}"
msg.split()         # by whitespace
```

---

**lists**

```python
nums = [1, 2, 3]
nums.append(4)
nums.insert(1, 7)
nums.remove(1)
nums.pop()
nums[0]
nums[1:3]
len(nums)
nums.sort()
nums.reverse()
2 in nums           # True
```

---

**tuples**

```python
t = (1, 2, 3)
t[0]
# immutable (can't change)
```

---

**dictionaries**

```python
d = {"one": 1, "two": 2}
d["two"]                # 2
d["three"] = 3
del d["one"]
d.get("four", 0)        # 0 if not found
d.keys()
d.values()
d.items()
```

---

**conditionals**

```python
if x > 0:
    print("positive")
elif x == 0:
    print("zero")
else:
    print("negative")
```

---

**loops**

```python
for item in my_list:
    print(item)

for i in range(5):          # 0 to 4
    print(i)

while condition:
    # block
    break                   # exit loop
    continue                # next iteration
```

---

**functions**

```python
def my_func(arg1, arg2=0):
    return arg1 + arg2

result = my_func(2)
```

---

**exceptions**

```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("division by zero")
except Exception as e:
    print(e)
finally:
    print("done")
```

---

**file handling**

```python
# write file
with open("file.txt", "w") as f:
    f.write("hello")

# read file
with open("file.txt", "r") as f:
    data = f.read()
```

---

**built-in functions**

- `print()`
- `input()`
- `type()`
- `len()`
- `str()`, `int()`, `float()`
- `list()`
- `dict()`
- `sum()`, `min()`, `max()`
- `range()`

---

**importing modules**

```python
import math
math.sqrt(16)

import random
random.randint(1, 10)

from datet
```