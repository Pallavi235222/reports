# 016 3Sum Closest

* * *
``Problem Statement``
  
<p>
Given an integer array nums of length n and an integer target, find three integers in nums such that the sum is closest to target.

Return the sum of the three integers.

You may assume that each input would have exactly one solution.
</p>

***

`Solution :`

```
#
class Solution(object):
    def threeSumClosest(self, nums, target):
        ls = len(nums)
        sort_nums = sorted(nums)
        res = nums[0] + nums[1] + nums[2]
        for i in range(ls - 2):
            j, k = i + 1, ls - 1
            while j < k:
                temp = sort_nums[i] + sort_nums[j] + sort_nums[k]
                if abs(target - temp) < abs(target - res):
                    res = temp
                if temp < target:
                    j += 1
                else:
                    k -= 1
        return res 


```

`Output:`

```
Input: nums = [-1,2,1,-4], target = 1
Output: 2
```

```
Input: nums = [0,0,0], target = 1
Output: 0
```


