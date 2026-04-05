I. Basics & Data Types

- **Output:** Use `print()` to display output.
    
    python
    

- ```
    print("Hello, World!") 
    ```
    
- **Comments:** Use `#` for single-line comments and `"""..."""` for multi-line comments.
- **Variables:** Assignment is done using the `=` operator.
    
    python
    
- ```
    message = "Hello, Python!"
    ```
    
- **Data Types:** Python has several built-in data types:
    - **Integers:** `x = 10`
    - **Floats:** `f = 5_123_456.789_123` (underscores for readability)
    - **Strings:** Ordered, immutable sequences of characters.
        
        python
        
- ```
    single = 'Hello'
    double = "World"
    multi = """Multiple line string"""
    ```
    
- **Booleans:** `True`, `False` 

II. Data Structures

- **Lists:** Ordered, mutable collections (`fruits = ["a", "b"]`). Methods include `.append()`, `.insert()`, `.pop()`, and `.remove()`.
- **Tuples:** Ordered, immutable collections (`coordinates = (4, 5)`).
- **Dictionaries:** Key-value pairs (`{"key": "value"}`).
- **Sets:** Unordered, unique collections (`{1, 2, 3}`). 

III. Control Flow

Python uses indentation for blocks. 

- **Conditional Statements:** `if`, `elif`, `else` for logic.
- **Loops:**
    - **For Loop:** `for i in range(5):`.
    - **While Loop:** `while condition:`.
    - **Control:** `break` stops, `continue` skips iterations. 

IV. Functions

Defined using `def`. 

python

```
def function_name(parameter):
    return result
```

V. File Handling

Utilize the `with` statement for automatic closing. 

python

```
with open("file.txt", "r") as f:
    content = f.read()
```

Comprehensive resources for further study include Python documentation, [Real Python](https://realpython.com/cheatsheets/python/), [QuickRef.ME](https://quickref.me/python.html), and [Java Code Geeks](https://www.javacodegeeks.com/core-python-cheatsheet.html).