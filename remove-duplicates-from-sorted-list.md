Remove Duplicates from Sorted List
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
    # @return a ListNode
    def deleteDuplicates(self, head):
        if head is None or head.next is None:
            return head
        cur = head
        ptr = head.next
        while ptr is not None:
            while ptr != None and cur.val == ptr.val:
                ptr = ptr.next
            cur.next = ptr
            cur = ptr
        return head
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
    # @return a ListNode
    def deleteDuplicates(self, head):
        if head is None or head.next is None:
            return head
        nhead = ListNode(0)
        nhead.next = head
        pre = nhead
        ptr = head
        while ptr is not None and ptr.next is not None:
            uniq = True
            while ptr.next != None and ptr.val == ptr.next.val:
                uniq = False
                ptr = ptr.next
            if uniq:
                pre.next = ptr
                pre = ptr
            ptr = ptr.next
        pre.next = ptr
        return nhead.next
```