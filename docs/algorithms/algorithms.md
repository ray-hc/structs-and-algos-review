# BFS/DFS

## Binary Search


```Python
def binary_search(arr, low, high, x):

    if low == None:
      low = 0
    if high == None:
      high = len(arr)-1
      
    if high >= low:
        mid = (high + low) // 2
        if arr[mid] == x:
            return mid
        elif arr[mid] > x:
            return binary_search(arr, low, mid - 1, x)
        else:
            return binary_search(arr, mid + 1, high, x)
    else:
        return -1         # Element is not present in the array
```

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

Uses: cycle detection in unweighted graph, GPS navigation, etc.

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

Uses:
* Cycle detection (not sure why) (BFS can't do this)

# Dijkstra's Algorithm


# BST Validator

```Python
class Solution(object):  
  def isValidBST(self, node, min=None, max=None):
      
      if not node:      # Validate the end of trees.
          return True

      if not min == None:
          if node.val <= min:
              return False

      if not max == None:
          if node.val >= max:
              return False

      leftValid = self.isValidBST(node.left, min, node.val)
      rightValid = self.isValidBST(node.right, node.val, max)

      return (leftValid and rightValid)
```