Find Minimum in Rotated Sorted Array
==

1.
--

```
class Solution:
    # @param num, a list of integer
    # @return an integer
    def findMin(self, num):
        if len(num) == 0:
            return None
        if len(num) == 1:
            return num[0]
        low, high = 0, len(num) - 1
        if num[low] < num[high]:
            return num[low]
        while low < high:
            if low + 1 == high:
                return min(num[low], num[high])
            mid = (low + high) / 2
            if num[mid] < num[high]:
                high = mid
            else:
                low = mid
        return None

    def rotate(self, nums, k):
        k %= len(nums)
        if k == 0:
            return
        pos = 0
        count = 0
        while count < len(nums):
            tag = pos
            cur = nums[pos]
            for i in range(len(nums)):
                target = (pos + k) % len(nums)
                tmp = nums[target]
                nums[target] = cur
                cur = tmp
                pos = target
                count += 1
                if tag == pos or count == len(nums):
                    break
            pos = (pos + 1) % len(nums)
```

2.
--

```
class Solution:
    # @param num, a list of integer
    # @return an integer
    def findMin(self, num):
        if len(num) == 0:
            return None
        if len(num) == 1:
            return num[0]
        low, high = 0, len(num) - 1
        if num[low] < num[high]:
            return num[low]
        def tryy(num, low, high):
            if low == high:
                return num[low]
            if low + 1 == high:
                return min(num[low], num[high])
            mid = (low + high) / 2
            if num[mid] < num[high]:
                return tryy(num, low, mid)
            elif num[mid] == num[high]:
                return min(tryy(num, low, mid), tryy(num, mid, high))
            else:
                return tryy(num, mid, high)
        return tryy(num, low, high)

    def rotate(self, nums, k):
        k %= len(nums)
        if k == 0:
            return
        pos = 0
        count = 0
        while count < len(nums):
            tag = pos
            cur = nums[pos]
            for i in range(len(nums)):
                target = (pos + k) % len(nums)
                tmp = nums[target]
                nums[target] = cur
                cur = tmp
                pos = target
                count += 1
                if tag == pos or count == len(nums):
                    break
            pos = (pos + 1) % len(nums)

```

