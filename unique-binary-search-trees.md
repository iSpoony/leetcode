Unique Binary Search Trees
==

1.
--

```
class Solution:
    # @return an integer
    def numTrees(self, n):
        if n <= 0:
            return 1
        f = {0:1, 1:1}
        for v in range(2, n + 1):
            f[v] = 0
            for i in range(v):
                f[v] += f[i] * f[v - i - 1]
        return f[n]
```

2.
--

```
# Definition for a  binary tree node
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    # @return a list of tree node
    def generateTrees(self, n):
        if n <= 0:
            return [None]
        return self.generateTreesWithRange(1, n)

    def generateTreesWithRange(self, low, high):
        if low > high:
            return [None]
        if low == high:
            return [TreeNode(low)]
        lst = []
        for i in range(low, high+1):
            for left in self.generateTreesWithRange(low, i - 1):
                for right in self.generateTreesWithRange(i + 1, high):
                    root = TreeNode(i)
                    root.left = left
                    root.right = right
                    lst.append(root)
        return lst
```
