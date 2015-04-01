Minimum Path Sum
==

```
class Solution:
    # @param grid, a list of lists of integers
    # @return an integer
    def minPathSum(self, grid):
        n = len(grid)
        if n == 0:
            return 0
        m = len(grid[0])
        if m == 0:
            return 0
        res = [[grid[i][j] for j in range(m)] for i in range(n)]
        for i in range(1, n):
            res[i][0] = res[i - 1][0] + grid[i][0]
        for j in range(1, m):
            res[0][j] = res[0][j - 1] + grid[0][j]
        for i in range(1, n):
            for j in range(1, m):
                res[i][j] = min(res[i - 1][j], res[i][j - 1]) + grid[i][j]

        return res[-1][-1]
```
