# Style Points and Helpful Code

## Unpacking

```python
for i, item in enumerate(some_list):
  # do something.
  # enumerate --> returns count of where you are + item.
```

## Swapping

```python
a, b = b, a
```

## Create a length-N list of the same thing

```python
four_nones = [None] * 4
```

  * If an object is mutable -- this will copy 4 references to list.

## Create a length-N list of lists 

```python
four_lists = [[] for __ in range(4)]
```

## Check style

```bash
pip install pycodestyle
pycodestyle program.py
```

## `None` evaluates to `False` (Falsey).

  * Can use `is None` if need to distinguish between `False`, `None`.
  * Else, `if element` or `if not element` is fine.

## Remove from list

```python
while i in a:
  a.remove(i)
```

## List Comprehension

```python
# Creates a new list object of filtered vals.
filtered_values = [value for value in sequence if value != x]
#
```

## Opening Files

```python
with open('file.txt') as f:
    for line in f:
        print(line)
```

  Always handles exceptions, and closes.

## "We are all responsible users"
  No such thing as "private" in Python.

## Use 4 spaces per indentation level.

## F Strings

```python
def greet_user(name):
print(f”Hi {name}”) 
```

## How to Do Random Variables

```python
import random
random.random() # returns a float between 0 to 1
random.randint(1, 6) # returns an int between 1 to 6 
```