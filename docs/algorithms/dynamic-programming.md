# Dynamic Programming

## Max Subset-Sum

Given an array of integers, find the subset of non-adjacent elements with the maximum sum. Calculate the sum of that subset.

```python
def maxSubsetSum(arr):
    
    optSums = [0] * len(arr)
    
    optSums[0] = max(0, arr[0])
    optSums[1] = max(0, arr[1])

    for i in range(2, len(arr)):
        optSums[i] = max(0, arr[i]) + optSums[i-2]
        if optSums[i] < optSums[i-1]:
            optSums[i] = optSums[i-1]
    
    return optSums[-1]
```

**Formula:** element may be negative (thus, never want to include). For each element, if you include, you cannot include previous element. Thus, `OPT` for element at index `i` is that element, plus the best up until `i-2`th element, or the best up until `i-1`.

## Candies

Alice wants to give some candies to the children in her class.  All the children sit in a line and each of them has a rating score.  Alice wants to give at least 1 candy to each child. If two children sit next to each other, then the one with the higher rating must get more candies. Alice wants to minimize the total number of candies she must buy.

```python
def findNextMin(idx, n, arr):

    x = idx
    while x < n-1 and arr[x] > arr[x+1]:
        x += 1
    return x

def candies(n, arr):

    opt = [1] * n
    idx = 0
    while idx < n-1:
        if arr[idx] > arr[idx+1]:
            nMin = findNextMin(idx, n, arr)
            for nIdx in range(idx, nMin):
                opt[nIdx] = max(opt[nIdx], nMin - nIdx + 1)
            idx = nMin
        elif arr[idx] < arr[idx+1]:
            opt[idx+1] = opt[idx]+1
            idx += 1
        elif arr[idx] == arr[idx+1]:
            idx += 1
    return sum(opt)
```

## Longest Common Subsequence

```python
def commonChild(s1, s2):

    opt = [[0]*(len(s1) + 1) for i in range(len(s2) + 1)]
    
    for idx1 in range(1, len(s1)+1):
        for idx2 in range(1, len(s2)+1):
                
            useCurr = 0
            if s1[idx1-1] == s2[idx2-1]:
                useCurr = opt[idx1-1][idx2-1] + 1
            
            opt[idx1][idx2] = max(useCurr, opt[idx1][idx2-1], opt[idx1-1][idx2])
                
    return opt[-1][-1]
```