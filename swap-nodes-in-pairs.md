Swap Nodes in Pairs
==

```
class Solution:
    # @param a ListNode
    # @return a ListNode
    def swapPairs(self, head):
        if head == None or head.next == None:
            return head
        nhead = ListNode(0)
        nhead.next = head
        pre = nhead
        ptr = head
        head = nhead
        while ptr != None and ptr.next != None:
            pnext = ptr.next
            post = pnext.next
            pre.next = pnext
            pnext.next = ptr
            ptr.next = post
            pre = ptr
            ptr = post
        return head.next
```
