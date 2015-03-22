Single Number
==

1. 除了1个数字，其他都出现2次，找出出现1次的数字
--

烂大街的思路：抑或

```
class Solution:
    # @param A, a list of integer
    # @return an integer
    def singleNumber(self, A):
        n = 0
        for i in A:
            n ^= i
        return n
```

2. 除了1个数字，其他都出现3次，找出这个数字
--

计数法没意思，求位法TODO
