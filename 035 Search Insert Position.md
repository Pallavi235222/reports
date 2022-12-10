# 035 Search Insert Position

* * *
``Problem Statement``
  
<p>
Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with O(log n) runtime complexity.
</p>

***

`Solution :`

```
# 
class Solution:
    def searchInsert(self, nums, target):
        l, r = int(0), len(nums) - 1
        while l < r:
            mid = int((l + r) / 2)
            if nums[mid] < target:
                l = mid + 1
            else:
                r = mid
        if nums[l] < target:
            return l + 1
        return l
#
```

`Output:`

```
Input: nums = [1,3,5,6], target = 5
Output: 2
```

```
Input: nums = [1,3,5,6],  target = 2
Output: 1
```

```
Input: nums = [1,3,5,6], target = 7
Output: 4
```
