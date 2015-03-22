Search Insert Position
==

```
class Solution:
    # @param A, a list of integers
    # @param target, an integer to be inserted
    # @return integer
    def searchInsert(self, A, target):
        for pos in range(len(A)):
            if A[pos] >= target:
                return pos
        return len(A)
```
