
# 014 Longest Common Prefix

* * *
``Problem Statement``
  
<p>
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

</p>

***

`Solution :`

```
# python

class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        ls = len(strs)
        if ls == 1:
            return strs[0]
        prefix = ''
        pos = 0
        while True:
            try:
                current = strs[0][pos]
            except IndexError:
                break
            index = 1
            while index < ls:
                try:
                    if strs[index][pos] != current:
                        break
                except IndexError:
                    break
                index += 1
            if index == ls:
                prefix = prefix + current
            else:
                break
            pos += 1
        return prefix

```

`Output:`

```
Input: strs = ["flower","flow","flight"]
Output: "fl"
```

```
Input: strs = ["dog","racecar","car"]
Output: ""
```