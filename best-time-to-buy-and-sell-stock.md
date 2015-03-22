Best Time to Buy and Sell Stock
==

###1 最多买卖1次

解1:

```
class Solution:
    # @param prices, a list of integer
    # @return an integer
    def maxProfit(self, prices):
        if len(prices) == 0:
            return 0
        minp, maxp = 0, 0
        maxVal = 0
        for p in range(1, len(prices)):
            if prices[p] < prices[minp]:
                minp = p
                maxp = p
            elif prices[p] >= prices[maxp]:
                maxp = p
            if minp < maxp:
                maxVal = max(maxVal, prices[maxp] - prices[minp])
        return maxVal
```

解2:

```
class Solution:
    # @param prices, a list of integer
    # @return an integer
    def maxProfit(self, prices):
        if len(prices) == 0:
            return 0
        diff = [prices[i] - prices[i - 1] for i in range(1, len(prices))]
        val = 0
        maxVal = 0
        for d in diff:
            if val + d < 0:
                val = 0
            else:
                val += d
                maxVal = max(maxVal, val)
        return maxVal
```


###2 买卖次数不限

解1:

```
class Solution:
    # @param prices, a list of integer
    # @return an integer
    def maxProfit(self, prices):
        if len(prices) == 0:
            return 0
        val = 0
        minp = prices[0]
        for p in prices[1:]:
            if minp < p:
                val += p - minp
            minp = p
        return val
```

解2:

```
class Solution:
    # @param prices, a list of integer
    # @return an integer
    def maxProfit(self, prices):
        if len(prices) == 0:
            return 0
        diff = [prices[i] - prices[i - 1] for i in range(1, len(prices))]
        val = 0
        for d in diff:
            if d > 0:
                val += d
        return val
```

###3 最多可买卖2次

TODO

###4 最多可买卖K次

TODO
