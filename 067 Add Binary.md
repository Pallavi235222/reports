# 067 Add Binary

* * *
``Problem Statement``
  
<p>
Given two binary strings a and b, return their sum as a binary string.
</p>

***

`Solution :`

```
# 
class Solution:
    def addBinary(self, a: str, b: str) -> str:
        result = ""
        carry = 0
        a, b = list(a), list(b)
        while a or b or carry:
            if a:
                carry += int(a.pop())
            if b:
                carry += int(b.pop())
            carry, remainder = divmod(carry, 2) 
            result += str(remainder)
        return result[::-1]
#
```

`Output:`

```
Input: a = "11" , b = "1"
Output: "100"
```

```
Input: a = "1010", b = "1011"
Output: "10101"
```


