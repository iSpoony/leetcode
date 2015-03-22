Populating Next Right Pointers in Each Node
==

```
# Definition for a  binary tree node
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None
#         self.next = None

class Solution:
    # @param root, a tree node
    # @return nothing
    def connect(self, root):
        if root is None:
            return
        queues = [[root],[]]
        tag = 0
        while len(queues[tag]) > 0:
            for node in queues[tag]:
                if node.left is not None:
                    queues[1-tag].append(node.left)
                if node.right is not None:
                    queues[1-tag].append(node.right)
            nextp = None
            while len(queues[tag]) > 0:
                node = queues[tag].pop()
                node.next = nextp
                nextp = node
            tag = 1 - tag
```
