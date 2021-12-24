# Heaps and Priority Queues

## The Heap

| Operation       | O-complexity |
| --------------- | ------------ |
| isEmpty         | O(1)         |
| insert          | O(log(n))    |
| extractMin/Max  | O(log(n))    |
| min/max         | O(1)         |

### Implementation 

#### Python's Built-In:

```Python
import heapq
...
heapq.heapify(list)
smallestElem = heapq.heappush(list, elem) # Add element
heapq.heappop(list) # Remove element from the heap

def heapsort(iterable):
    h = []
    for value in iterable:
          heappush(h, value)
    return [heappop(h) for i in range(len(h))]
```

#### DIY

```Python
def min_heapify(A,k):
    l = left(k)
    r = right(k)
    if l < len(A) and A[l] < A[k]:
        smallest = l
    else:
        smallest = k
    if r < len(A) and A[r] < A[smallest]:
        smallest = r
    if smallest != k:
        A[k], A[smallest] = A[smallest], A[k]
        min_heapify(A, smallest)

def left(k):
    return 2 * k + 1

def right(k):
    return 2 * k + 2

def build_min_heap(A):
    n = int((len(A)//2)-1)
    for k in range(n, -1, -1):
        min_heapify(A,k)

A = [3,9,2,1,4,5]
build_min_heap(A)
print(A)
```

Got from [here](https://favtutor.com/blogs/heap-in-python).

## Priority Queue

Implemented using max-heap.

**Uses:**

* Looking for the top k items in a list
* Simulations, scheduling
