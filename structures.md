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
class Node:
   def __init__(self, data=None):
      self.data = data
      self.next = None

class SLinkedList:
   def __init__(self):
      self.head = None

    def add_node(self, node):
      if (self.head == None):
        self.head = node
      else:
        ptr = self.head
        while self.next != None:
          ptr = self.next
        ptr.next = node
```


## Hashtable

**Salting:** multiplying the hash with a random integer so that even if a hacker knew what common passwords were and their corresponding hashes, they couldn't just map them.

**Open Addressing:** 
  * Insertion: go to the hash-slot, but keep iterating down until you find an open slot. 
  * Retrieval: go to the hash-slot, but if it's not there, iterate until you hit a *None* box.
  * Deletion: when deleting, fill with a dummy-variable that isn't *None* that you know means can overwrite if insertion but pretend is full for purpose of retrieval.

### Implementation

#### Hard-coded:
```Python
class Hashtable:
    def __init__(self, bucket_size):
      self.bucket_size = bucket_size
      self.buckets = [[] for i in range(self.bucket_size)]    # create empty buckets

    
    def save_key_val_pair(self, key, value):
      hashed_val = hash(key)
      bIndex = hashed_val % self.bucket_size
      self.buckets[bIndex].append((key, value))

    def get_value(self, key):
      hashed_value = hash(key)
        bIndex = hashed_value % self.bucket_size
        bucket = self.buckets[bIndex]
        for key, value in bucket:
            if key == input_key:
                return(value)
        return None
```

#### Built-in
Use a dictionary, implemented w/ hashtable. 
Can use `for (k, v) in dict.items():` or `for key in dict.keys()`.
`del dict[key]` to delete.

