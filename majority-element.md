Majority Element
==

```
class Solution:
    # @param num, a list of integers
    # @return an integer
    def majorityElement(self, num):
        if len(num) == 0:
            return None
        val = num[0]
        count = 0
        for n in num:
            if val == n:
                count += 1
            else:
                count -= 1
            if count < 0:
                val = n
                count = 0
        return val
```