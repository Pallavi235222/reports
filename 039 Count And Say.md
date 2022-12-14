# 039 Count And Say

* * *
``Problem Statement``
  
<p>
The count-and-say sequence is a sequence of digit strings defined by the recursive formula:

countAndSay(1) = "1"
countAndSay(n) is the way you would "say" the digit string from countAndSay(n-1), which is then converted into a different digit string.
To determine how you "say" a digit string, split it into the minimal number of substrings such that each substring contains exactly one unique digit. Then for each substring, say the number of digits, then say the digit. Finally, concatenate every said digit.

For example, the saying and conversion for digit string "3322251":


Given a positive integer n, return the nth term of the count-and-say sequence.
</p>

***

`Solution :`

```
# 
class Solution:
    def countAndSay(self, n):
        if n == 1:
            return '1'
        x = '1'
        while n > 1:
            x = self.count(x)
            n -= 1
        return x
    def count(self, x):
        m = list(x)
        res = []
        m.append(None)
        i,j = 0,0
        while i < len(m) - 1:
            j += 1
            if m[j] != m[i]:
                res += [j - i, m[i]]
                i = j
        return ''.join(str(s) for s in res)
#
```

`Output:`

```
Input: n = 1
Output: "1"
```

```
Input: n = 4
Output: "1211"
```


