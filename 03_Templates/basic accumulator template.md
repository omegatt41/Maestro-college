basic accumulator template
```python 
# 1) Define your helper: does work for ONE item and returns a value
def process_item(item):
    # Do some work with this single item
    # e.g. transform, calculate, format, etc.
    result = ...  # use item to compute something
    return result

# 2) Prepare your collection and any accumulators
items = [...]          # e.g. [10, 5, 20]
accumulator = 0        # or [] / "" / whatever makes sense

# 3) Loop: delegate per-item work to the helper
for item in items:
    processed = process_item(item)   # call helper

    # Use the result AFTER the helper call
    # Example patterns:
    # accumulator += processed
    # accumulator.append(processed)
    # print(processed)
    ...

# 4) After the loop, use the accumulator if you have one
print(accumulator)
```

with price+tax template
```python
def add_tax(amount):
    return amount * 1.1

def format_price_with_tax(amount):
    with_tax = add_tax(amount)
    return f"Original price: ${amount}, with tax {with_tax}"

prices = [10, 5, 20]
total_with_tax = 0

for price in prices:
    with_tax = add_tax(price)            # helper 1: numeric result
    total_with_tax += with_tax           # accumulator update

    line = format_price_with_tax(price)  # helper 2: formatted string
    print(line)

print(f"Total: ${total_with_tax}")

```