Remove Duplicates from Sorted Array
==

1.
--

```
class Solution:
    # @param a list of integers
    # @return an integer
    def removeDuplicates(self, A):
        if len(A) == 0:
            return 0
        pos, p = 0, 1
        while p < len(A):
            if A[p] != A[pos]:
                A[pos+1] = A[p]
                pos += 1
            p += 1
        for i in range(len(A)-pos-1):
            A.pop()
        return pos+1
```

2.
--

```
class Solution:
    # @param A a list of integers
    # @return an integer
    def removeDuplicates(self, A):
        if len(A) <= 1:
            return len(A)
        pos, p = 0, 0
        while p < len(A):
            A[pos] = A[p]
            pos += 1
            cur = p + 1
            while cur < len(A) and A[cur] == A[p]:
                cur += 1
            if cur > p + 1:
                A[pos] = A[p]
                pos += 1
            p = cur
        return pos
```
