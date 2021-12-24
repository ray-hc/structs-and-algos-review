# Sorting

## QuickSort

```Python
def partition(arr, st, end):
    
    piv = arr[end]
    i = st - 1
    
    for j in range(st, end + 1):
        if arr[j] <= piv:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]    
            
    return i

def quickSort(arr, st = 0, end = None):
    
    if end == None:
        end = len(arr) - 1
        
    if (end - st) < 1:
        return
    
    i = partition(arr, st, end)
    quickSort(arr, st, i-1)
    quickSort(arr, i+1, end)
```

## MergeSort
* Divide array into 2 equal-sized subarrays
* Recursively sort subarrays
* Merge in one pass

```Python
def mergeSort(arr):
    
    if len(arr) == 1:
        return
        
    mid = len(arr)//2
    left = arr[:mid]
    right = arr[mid:]
    
    mergeSort(left)
    mergeSort(right)
    
    i = j = k = 0
    while i < len(left) or j < len(right):
        if i >= len(left):
            arr[k] = right[j]
            j += 1
        elif j >= len(right):
            arr[k] = left[i]
            i += 1
        elif left[i] < right[j]:
            arr[k] = left[i]
            i += 1
        else: # left[i] > right[j]
            arr[k] = right[j]
            j += 1
            
        k += 1
        
    return
```

## Bubble Sort

```Python
def bubbleSort(a):
    for i in range(len(a)):
        for j in range(len(a)-1):
            if a[j] > a[j+1]:
                a[j], a[j+1] = a[j+1], a[j]
```