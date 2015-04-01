Balanced Binary Tree
==

Solution 1:
--

```
class Solution:
    # @param root, a tree node
    # @return a boolean
    def isBalanced(self, root):
        return depth0(root)[0]

def depth0(node):
    if node is None:
        return (True, 0)
    (leftB, leftD) = depth0(node.left)
    if not leftB:
        return (False, -1)
    (rightB, rightD) = depth0(node.right)
    if not rightB:
        return (False, -1)
    if abs(leftD - rightD) <= 1:
        return (True, max(leftD, rightD) + 1)
    return (False, -1)
```

Solution 2:
--

`self.balance`全局变量

```
class Solution:
    def __init__(self):
        self.balance = True
    # @param root, a tree node
    # @return a boolean
    def isBalanced(self, root):
        if root is not None:
            self.depth(root)
        return self.balance

    def depth(self, node):
        if node is None:
            self.balance &= True
            return 0
        ld = self.depth(node.left)
        rd = self.depth(node.right)
        self.balance &= (abs(ld - rd) <= 1)
        return max(ld, rd) + 1
```
