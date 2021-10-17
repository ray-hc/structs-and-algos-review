## Binary Trees

A **complete tree**: nodes filled in left to right, all but last level are full.
log_2(n+1)=h, where n = number of nodes, h = tree height. (round up!)

**Visiting In Order:**
```Python
# In Node class
def visitInOrder(self):
  if self.left:
    self.left.visitInOrder()
  print(self.val)         # Do whatever you want to do.
  if self.right:
    right.visitInOrder()
```