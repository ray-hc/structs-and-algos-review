## Plain Ol' Lists
In Python, `if item in list` takes a long time. Try to use `if item in set`.

Python built-in time complexities [here](https://wiki.python.org/moin/TimeComplexity?).

## Linked Lists

| Operation   | O-complexity |
| ----------- | ------------ |
| Space       | O(n)         |
| Pre-/append | O(1)         |
| Lookup      | O(n)         |
| Insert      | O(n)         |
| Delete      | O(n)         |

Ideal for stacks and queues.

### Stacks

| Operation   | O-complexity |
| ----------- | ------------ |
| Push        | O(1)         |
| Pop         | O(1)         |
| Peek        | O(1)         |

**Last In, First Out**
**Uses:** Call stack (of functions), depth first search

Implement as a linked list -- insert, remove at the head.

#### Implementation
```Python
class SLinkedList:
   def __init__(self):
      self.head = None
      self.rear = None

    def add_node(self, node):
      if (self.head == None):
        self.head = node
      else:
        ptr = self.head
        while self.next != None:
          ptr = self.next         # Skip to end of list.
        ptr.next = node
```

### Queues

| Operation   | O-complexity |
| ----------- | ------------ |
| Enqueue     | O(1)         |
| Dequeue     | O(1)         |
| Peek        | O(1)         |

**First In, First Out**
**Uses:** Breadth First Search, printers, web servers (replying to requests in order).

#### Implementation
Implement as a linked list -- insert at the tail, remove at the head.

```Python
class QueueLnkdLst:
   def __init__(self):
      self.head = None
      self.rear = None

    def enqueue(self, node):
      if (self.head == None):
        self.head = node
        self.rear = node
      else:
        self.rear.next = node
        self.rear = node
```

Or implement as an array. (This code is untested/confirmed, and unsure if Python list implementation makes necessary.)
**Conceptually:** Mantain pointers to head/rear of list, and bump accccordingly.

```Python
class QueueArray:
   def __init__(self):
      self.q = [""] * 10            # Make queue with 10 slots.
      self.head = 0
      self.rear = 0
      self.size = 0

    def enqueue(self, item):
      self.q[rear] = item
      self.rear += 1
      self.size += 1
      if self.rear == len(self.q):         # If we reached end of array, loop back.
        self.rear = 0
      if self.rear == self.head and self.size > 0:
        print("Error, exceeded queue size")
```
