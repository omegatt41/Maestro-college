---
type: lecture
class: "[[Software Engineering]]"
tags:
  - SE
  - lecture
  - 2026-05-16
date: 2026-05-16 17:25
topics: []
---
# dict-list-comprehesion

## 📌 Overview
*   **Course:** SE
*   **Lecture Date:** 2026-05-16 
*   **Instructor:** maestro

## 🎯 Learning Objectives
*   refactoring messy code using helpers and list and dict comprehension to make it more compact and readable

## 📝 Notes
*   **unction Pipelines (Tracing)**

- Always evaluate inner functions first, then move outward.
- Example:
    
    ```python
    result = square(minus3(times2(add1(4))))
    # Step-by-step:
    # add1(4) → times2(...) → minus3(...) → square(...)
    ```
    
- Write out each intermediate step when tracing.

**Refactoring Code**

- Each function (helper) should do one clearly defined job.
- Keep all `print()` or other I/O in your `main()` function.
- Remove duplicated logic.
- Good function names should match what the function actually returns.

**List Comprehension**

- Build a list in one line: `[expression for item in list if condition]`
- Example:
    
    ```python
    paid_orders = [order for order in orders if order['status'] == 'PAID']
    ```
    

**Dictionary Comprehension**

- Make a dictionary in one line:
    
    ```python
    result = {key: value for key in iterable}
    ```
    
- For grouping, you might combine with set:
    
    ```python
    customers = {order['customer'] for order in orders}
    totals = {customer: sum(order['amount'] for order in orders if order['customer'] == customer) for customer in customers}
    ```
    

**Sorting with Keys**

- Use `sorted()` with `key=...` and `reverse=True` to sort by values:
    
    ```python
    sorted_customers = sorted(totals.items(), key=lambda item: item[1], reverse=True)
    top_n = [customer for customer, amount in sorted_customers[:n]]
    ```
    

**Good Habits**

- Break up big problems into helpers for each task.
- Test and print results after each helper to isolate bugs.
- Be deliberate with naming—spelling matters for clarity!
- Try both comprehensions and loops, and choose the one that's clearest for you and your team.

**To Practice More**

- Trace more pipelines with nested functions.
- Turn more loops into list/dict comprehensions for practice.
- Refactor old scripts to separate logic into helpers and keep main tidy.

## 💻 Code Examples / Algorithms
```python
def filter_paid(orders):
    '''keep only paid orders'''
    paid_orders = [order for order in orders if order['status'] == 'PAID']
    return paid_orders

def group_totals(orders):
    customers = {order['customer'] for order in orders}
    return {customer: sum(order['amount'] for order in orders if order['customer'] == customer) for customer in customers}

def top_customers(totals, n):
    '''return a list of the top customer names, sorted high to low'''
    # sort in decending order
    sorted_customers = sorted(totals.items(), key=lambda item: item[1], reverse= True)
    #extract only the names for the top n customers
    return [customer for customer, total in sorted_customers[:n]]

def main():
    orders = [
    {"customer": "Alice", "amount": 60, "status": "PAID"},
    {"customer": "Bob", "amount": 30, "status": "PENDING"},
    {"customer": "Alice", "amount": 40, "status": "PAID"},
    {"customer": "Dana", "amount": 70, "status": "PAID"},
    {"customer": "Bob", "amount": 35, "status": "PAID"},
    {"customer": "Charlie", "amount": 105, "status": "PAID"}
]
    #1. filter out unpaid orders
    paid_orders = filter_paid(orders)

    #2. Calculate totals per customer
    totals = group_totals(paid_orders)

    #3. Get the top three spenders
    top_3 = top_customers(totals, 3)

    #print final result
    print(top_3)

if __name__ == '__main__':
    main()
```
NOTES:
	- practice more list and dict comprehensions
	- practice more refactoring
	- practice more pseudocode and program building
