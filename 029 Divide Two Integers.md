# 029 Divide Two Integers

* * *
``Problem Statement``
  
<p>
Given two integers dividend and divisor, divide two integers without using multiplication, division, and mod operator.

The integer division should truncate toward zero, which means losing its fractional part. For example, 8.345 would be truncated to 8, and -2.7335 would be truncated to -2.

Return the quotient after dividing dividend by divisor.

Note: Assume we are dealing with an environment that could only store integers within the 32-bit signed integer range: [−231, 231 − 1]. For this problem, if the quotient is strictly greater than 231 - 1, then return 231 - 1, and if the quotient is strictly less than -231, then return -231.

 
</p>

***

`Solution :`

```
# 
class Solution(object):
    def divide(self, dividend, divisor):
        (dividend >= 0)^(divisor < 0)
        isPositive = (dividend < 0) == (divisor < 0)
        dividend, divisor, result = abs(dividend), abs(divisor), 0
        while dividend >= divisor:
            n, nb = 1, divisor
            while dividend >= nb:
                dividend, result = dividend - nb, result + n 
                n, nb = n << 1, nb << 1
        if isPositive:
            return min(result,2147483647)
        return max(-result, -2147483648)
#
```

`Output:`

```
Input: dividend = 10,divisor = 3
Output: 3
```

```
Input: dividend = 7, divisor = -3
Output: -2
```


