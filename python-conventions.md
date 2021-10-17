# Style Points

* Unpacking
  ```Python
  for i, item in enumerate(some_list):
    # do something.
    # enumerate --> returns count of where you are + item.
  ```
* Swapping
  ```Python
  a, b = b, a
  ```
* Create a length-N list of the same thing
  ```Python
  four_nones = [None] * 4
  ```
  * If an object is mutable -- this will copy 4 references to list.

* Create a length-N list of lists 
  ```Python
  four_lists = [[] for __ in range(4)]
  ```

* Check style
  ```bash
  pip install pycodestyle
  pycodestyle program.py
  ```

* `None` evaluates to `False` (Falsey).
  * Can use `is None` if need to distinguish between `False`, `None`.
  * Else, `if element` or `if not element` is fine.

* Remove from list
  ```Python
  while i in a:
    a.remove(i)
  ```

* List Comprehension
  ```Python
  # Creates a new list object of filtered vals.
  filtered_values = [value for value in sequence if value != x]
  #
  ```

* Opening Filess
  ```Python
  with open('file.txt') as f:
      for line in f:
          print(line)
  ```
  Always handles exceptions, and closes.

* "We are all responsible users"
  No such thing as "private" in Python.