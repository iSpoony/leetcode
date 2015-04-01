Remove Element
==

```
class Solution:
    # @param    A       a list of integers
    # @param    elem    an integer, value need to be removed
    # @return an integer
    def removeElement(self, A, elem):
        i, j = 0, len(A) - 1
        while i <= j:
            while j > i and A[j] == elem:
                j -= 1
                A.pop()
            if A[i] == elem:
                A[i] = A[j]
                j -= 1
                A.pop()
            i += 1
        return j + 1
```
