Climbing Stairs
==

```
class Solution:
    # @param n, an integer
    # @return an integer
    def climbStairs(self, n):
        if n <= 0:
            return 0
        f = {1:1, 2:2}
        for i in range(3, n + 1):
            f[i] = f[i - 1] + f[i - 2]
        return f[n]
```
