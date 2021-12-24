# Trees

## Binary Search Tree Validator

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