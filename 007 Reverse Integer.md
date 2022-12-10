# 007 Reverse Integer

* * *
``Problem Statement``
  
<p>
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).
</p>

***

`Solution :`

```
# 
class Solution:
    def reverse(self, x):
        flag = True if x < 0 else False
        if flag:
            x = -x
        x = str(x)[::-1]
        if flag:
            x = "-" + x
        value = 2 ** 31
        x = int(x)
        if -value <= x < value:
            return x
        return 0
#
```

`Output:`

```
Input: x = 123
Output: 321
```

```
Input: x = -123
Output: -321
```

```
Input: x = 120
Output: 21
```
