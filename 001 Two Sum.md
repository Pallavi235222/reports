# 001 Two Sum

* * *
``Problem Statement``
  
<p>
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.
</p>

***

`Solution :`

```
# python

class Solution:
    def twoSum(self, nums, target): 
        visited = {}  
        i=0
        while i < len(nums): 
            val = target - nums[i] 
            if(val in visited):
                return(visited[val],i)
            visited[nums[i]] = i
            i+=1
        
```

`Output:`

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
```

```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

```
Input: nums = [3,3], target = 6
Output: [0,1]
```
