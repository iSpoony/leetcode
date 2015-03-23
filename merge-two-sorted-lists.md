Merge Two Sorted Lists
==

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    # @param two ListNodes
    # @return a ListNode
    def mergeTwoLists(self, l1, l2):
        head = ListNode(0)
        head.next = None
        ptr = head
        while l1 is not None and l2 is not None:
            if l1.val < l2.val:
                ptr.next = l1
                l1 = l1.next
            else:
                ptr.next = l2
                l2 = l2.next
            ptr = ptr.next
        if l1 is not None:
            ptr.next = l1
        else:
            ptr.next = l2
        return head.next
```