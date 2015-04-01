Permutations
==

```
class Solution:
    # @param num, a list of integer
    # @return a list of lists of integers
    def permute(self, num):
        if len(num) == 0:
            return [[]]
        if len(num) == 1:
            return [num]
        lst = [res[:p] + [num[0]] + res[p:] for p in range(len(num)) for res in self.permute(num[1:])]
        return lst

    def permute0(self, num):
        n = len(num)
        if n < 1:
            return [num]
        result = {}
        result[1] = [[1]]
        for i in range(2, n+1):
            res = []
            for r in result[i-1]:
                for k in range(len(r)+1):
                    tmp = r[0:k] + [i] + r[k:]
                    res.append(tmp)
            result[i] = res
        number = []
        for r in result[n]:
            number.append([num[p-1] for p in r])
        return number
```
