Unique Paths
==

```
class Solution:
    # @return an integer
    def uniquePaths(self, m, n):
        if m < 1 or n < 1:
            return 0
        f = [[1 for i in range(n+1)] for j in range(m+1)]
        for i in range(1, m):
            for j in range(1, n):
                f[i][j] = f[i-1][j] + f[i][j-1]
        print f
        return f[m-1][n-1]
```
