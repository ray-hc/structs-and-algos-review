# Stacks and Queues

## Stacks

**Last In, First Out**

| Operation   | O-complexity |
| ----------- | ------------ |
| Push        | O(1)         |
| Pop         | O(1)         |
| Peek        | O(1)         |

**Uses:** Call stack (of functions), depth first search

### Implementation

#### Python's Built-In

```Python
from collections import deque
 
stack = deque()
stack.append('c')
stack.pop()
```

#### DIY

Implement as a linked list -- insert and remove at the head.

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

## Queues

**First In, First Out**

| Operation   | O-complexity |
| ----------- | ------------ |
| Enqueue     | O(1)         |
| Dequeue     | O(1)         |
| Peek        | O(1)         |

**Uses:** Breadth First Search, printers, web servers (replying to requests in order).

### Implementation

#### Python's Built-In

```Python
from collections import deque

q = deque()
q.append('c')
q.popleft()
```

#### DIY

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

Can also implement as an array, where you mantain pointers to head/rear of list, and bump accccordingly.