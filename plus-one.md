Plus One
==

```
class Solution:
    # @param digits, a list of integer digits
    # @return a list of integer digits
    def plusOne(self, digits):
        result = []
        c = 1
        l = len(digits)
        for i in range(l):
            res = digits[l-i-1] + c
            c = res / 10
            result.append(res%10)
        if c > 0:
            result.append(c)
        result.reverse()
        return result
```
