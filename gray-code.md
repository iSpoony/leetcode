Gray Code
==

生成格雷码0-1数组

```
class Solution:
    # @return a list of integers
    def grayCode(self, n):
        if n < 0:
            return 0
        result = {}
        result[0] = [[0]]
        result[1] = [[0],[1]]
        for i in range(2, n + 1):
            base = result[i - 1]
            res0 = [[0] + b for b in base]
            base.reverse()
            res1 = [[1] + b for b in base]
            result[i] = res0 + res1
        vals = []
        for seq in result[n]:
            v = 0
            for b in seq:
                v = v * 2 + b
            vals.append(v)
        return vals
```
