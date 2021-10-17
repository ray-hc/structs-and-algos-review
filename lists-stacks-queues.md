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
class SLinkedList:
   def __init__(self):
      self.head = None
      self.rear = None

    def add_node(self, node):
      if (self.head == None):
        self.head = node
        self.rear = node
      else:
        self.rear.next = node
        self.rear = node
```