Container With Most Water
==

```
class Solution:
    # @return an integer
    def maxArea(self, height):
        l, h = 0, len(height) - 1
        val = 0
        while l < h:
            val = max(val, min(height[l], height[h]) * (h - l))
            if height[l] < height[h]:
                l += 1
            else:
                h -= 1
        return val
```
