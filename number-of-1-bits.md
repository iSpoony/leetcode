Number of 1 Bits
==

```
class Solution:
    # @param n, an integer
    # @return an integer
    def hammingWeight(self, n):
        w = 0
        while n != 0:
            if n & 1 == 1:
                w += 1
            n >>= 1
        return w
```
