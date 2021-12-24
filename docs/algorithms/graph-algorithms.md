# Graphs

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

* Cycle detection

## Dijkstra's Algorithm