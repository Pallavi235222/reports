
# 006 ZigZag Conversion

* * *
``Problem Statement``
  
<p>
The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)

```
P   A   H   N
A P L S I I G
Y   I   R
```
And then read line by line: "PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:
`
string convert(string s, int numRows);
`
</p>

***

`Solution :`

```
# python

class Solution(object):
    def convert(self,s,numRows):
        if numRows == 1:
            return s
        p = 2 * (numRows - 1)
        result = [""] * numRows
        for i in range(len(s)):
            floor = i % p
            if floor >= p//2:
                floor = p - floor
            result[floor] += s[i]
        return "".join(result)

```

`Output:`

```
Input: s = "PAYPALISHIRING", numRows = 3
Output: "PAHNAPLSIIGYIR"
```

```
Input: s = "PAYPALISHIRING", numRows = 4
Output: "PINALSIGYAHRPI"
```

```
Input: s = "A", numRows = 1
Output: "A"
```
