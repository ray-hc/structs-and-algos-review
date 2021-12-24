# Searching

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