Maximum Subarray
==

```
class Solution:
    # @param A, a list of integers
    # @return an integer
    def maxSubArray(self, A):
        if len(A) == 0:
            return 0
        val = 0
        maxv = A[0]
        for a in A:
            if a + val <= 0:
                val = 0
                maxv = max(maxv, a)
            else:
                val += a
                maxv = max(val, maxv)
        return maxv
```