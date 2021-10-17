# interview-prep


# Hashtable - Python

## Implementation

### Hard-coded:
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

### Built-in
Use a dictionary, implemented w/ hashtable. 
Can use `for (k, v) in dict.items():` or `for key in dict.keys()`.
`del dict[key]` to delete.

**Salting:** multiplying the hash with a random integer so that even if a hacker knew what common passwords were and their corresponding hashes, they couldn't just map them.
**Open Addressing:** 
  * Insertion: go to the hash-slot, but keep iterating down until you find an open slot. 
  * Retrieval: go to the hash-slot, but if it's not there, iterate until you hit a *None* box.
  * Deletion: when deleting, fill with a dummy-variable that isn't *None* that you know means can overwrite if insertion but pretend is full for purpose of retrieval.

# BFS/DFS

## Breadth-First Search
Implemented with adj. list format:
```Python
def bfs(visited = set(), graph, node): #function for BFS
  visited.add(node)
  queue.append(node)

  while queue:
    node = queue.pop(0) 
    for neighbour in graph[node]:
      if neighbour not in visited:
        visited.add(neighbour)
        queue.append(neighbour)
```
Got from [here](https://favtutor.com/blogs/breadth-first-search-python).

## Depth-First Search
Implemented with adj. list format:
```Python
def dfs(graph, start, target, path, visited = set()):
    path.append(start)
    visited.add(start) 
    if start == target:
        return path
    for neighbour in graph[start]:
        if neighbour not in visited:
            result = dfs(adj_list, neighbour, target, path, visited)
            if result is not None:
                return result
	  path.pop() # If we haven't returned by here, the current node is not on path to target.
    return None
```
Got from [here](https://stackabuse.com/depth-first-search-dfs-in-python-theory-and-implementation/).
