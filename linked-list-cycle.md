Linked List Cycle
==

1.
--

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    # @param head, a ListNode
    # @return a boolean
    def hasCycle(self, head):
        p1, p2 = head, head
        while p2 is not None and p2.next is not None:
            p1 = p1.next
            p2 = p2.next.next
            if p1 is p2:
                return True
        return False
```

2.
--

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    # @param head, a ListNode
    # @return a list node
    def detectCycle(self, head):
        p1, p2 = head, head
        while p2 is not None and p2.next is not None:
            p1 = p1.next
            p2 = p2.next.next
            if p1 is p2:
                break
        if p2 is None or p2.next is None:
            return None
        p2 = head
        while p1 is not p2:
            p1 = p1.next
            p2 = p2.next
        return p1
```
