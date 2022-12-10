
# 004 Median of Two Sorted Arrays

* * *
``Problem Statement``
  
<p>
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

</p>

***

`Solution :`

```
# python

class Solution(object):
    def findMedianSortedArrays(self,nums1,nums2):
        ls1, ls2 = len(nums1), len(nums2)
        if ls1 < ls2:
            return self.findMedianSortedArrays(nums2, nums1)
        l,r = 0, ls2*2
        while l <= r:
            mid2 = (l + r) >> 1
            mid1 = ls1 + ls2 - mid2
            L1 = -sys.maxsize - 1 if mid1 == 0 else nums1[(mid1 - 1) >> 1]
            L2 = -sys.maxsize - 1 if mid2 == 0 else nums2[(mid2 - 1) >> 1]
            R1 = sys.maxsize if mid1 == 2 * ls1 else nums1[mid1 >> 1]
            R2 = sys.maxsize if mid2 == 2 * ls2 else nums2[mid2 >> 1]
            if L1 > R2:
                l = mid2 + 1
            elif L2 > R1:
                r = mid2 - 1
            else:
                return (max(L1,L2) + min(R1, R2)) / 2.0
   

```

`Output:`

```
Input: nums1 = [1,3], nums2 = [2]
Output: 2.00000
```

```
Input: nums1 = [1,2], nums2 = [3,4]
Output: 2.50000
```

```
Input: nums1 = [1,3,5,8], nums2 = [2]
Output: 3.00000
```
