Symmetric Tree
==

```
# Definition for a  binary tree node
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    # @param root, a tree node
    # @return a boolean
    def isSymmetric(self, root):
        if root is None or (root.left is None and root.right is None):
            return True
        if not (root.left is not None and root.right is not None):
            return False
        leftLst = [root.left]
        rightLst = [root.right]
        while leftLst:
            ln = leftLst.pop(0)
            rn = rightLst.pop(0)
            if ln is None and rn is None:
                continue
            if ln is None or rn is None:
                return False
            if ln.val != rn.val:
                return False
            leftLst.append(ln.left)
            leftLst.append(ln.right)
            rightLst.append(rn.right)
            rightLst.append(rn.left)

        if len(leftLst) + len(rightLst) > 0:
            return False
        return True
```