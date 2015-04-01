Generate Parentheses
==

递推

```
class Solution:
    # @param an integer
    # @return a list of string
    def generateParenthesis(self, n):
        if n <= 0:
            return ""
        result = {}
        result[1] = ["()"]
        for i in range(2, n+1):
            res = []
            res += ["("+r+")" for r in result[i-1]]
            for j in range(1, i):
                res += [rj+rk for rk in result[i-j] for rj in result[j]]
            res = list(set(res))
            result[i] = res
        return result[n]
```
