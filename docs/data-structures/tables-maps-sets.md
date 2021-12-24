# Tables, Maps, and Sets

## Set (Abstract Data Type)

| Operation   | O-complexity |
| ----------- | ------------ |
| Space       | O(n)         |
| Add(e)      | O(h)         |
| Contains(e) | O(h)         |
| isEmpty     | O(1)         |
| Remove(e)   | O(h)         |
| Size        | O(1)         |

Where h is the height of binary tree, if binary tree used for implementation. 

### Python Implementation

In Python, set implemented with hashtable.

```Python
aSet = set()

aSet.add("banana")
print("Banana in set:", "banana" in aSet)

for x in aSet:
  print x # iterate over values in set

someItem = aSet.pop() # removes any item from the set.
aSet.remove("banana") # removes specific item.
# aSet.discard("banana") does not throw error on missing.

bSet = {"orange"}
union = aSet.union(bSet) # get union of sets
intersection = aSet.intersection(bSet)

aaSet = aSet.copy() # duplicate set
print("Length is", len(set)) # get length
```


## Map (Abstract Data Type)
| Operation        | O-complexity |
| ---------------- | ------------ |
| ContainsKey(key) | O()         |
| ContainsVal(val) | O()         |
| Get(key)         | O()         |
| isEmpty()        | O()         |
| keySet()         | O()         |
| put(key, val)    | O()         |
| remove(key)      | O()         |

## Hashtable

**Salting:** multiplying the hash with a random integer so that even if a hacker knew what common passwords were and their corresponding hashes, they couldn't just map them.

**Open Addressing:** 
  * Insertion: go to the hash-slot, but keep iterating down until you find an open slot. 
  * Retrieval: go to the hash-slot, but if it's not there, iterate until you hit a *None* box.
  * Deletion: when deleting, fill with a dummy-variable that isn't *None* that you know means can overwrite if insertion but pretend is full for purpose of retrieval.

**Amortized analysis**: When we get the worst-case runtimes, i.e. because we're expanding the table, this will pay dividends in faster time later that get averaged out. 

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

#### Python Implementation

Implemented using a hashtable.

```Python
aDict = dict()
aDict["a"] = "apple"
aDict.get("banana", "not there") # get key (or default value)

for key in aDict: # or "for key in newDict.keys():"
  print(key, aDict[key])
for (key, value) in aDict.items():
  print(key, value)

del dict["a"] # delete key/value pair.

print(len(aDict)) # get number of items
```