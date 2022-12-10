# 009 Palindrome Number

* * *
``Problem Statement``
  
<p>
Given an integer x, return true if x is a 
palindrome
, and false otherwise.
</p>

***

`Solution :`

```
# 
class Solution(object):
    def isPalindrome(self,x: int) -> bool:
        x = str(x)
        if (x == x[::-1]):
            return True
        return False
#
```

`Output:`

```
Input: x = 121
Output: True
```

```
Input: x = -121
Output: false
```

```
Input: x = 10
Output: false
```
