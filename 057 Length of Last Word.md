# 057 Length of Last Word 

* * *
``Problem Statement``
  
<p>
Given a string s consisting of words and spaces, return the length of the last word in the string.

A word is a maximal 
substring
 consisting of non-space characters only.
</p>

***

`Solution :`

```
# 
class Solution:
    def lengthOfLastWord(self, s: str) -> int:
        processedstr = s.strip()
        length = 0
        for i in range(len(processedstr)):
            if processedstr[i] == " ":
                length = 0
            else:
                length +=1
        return length
#
```

`Output:`

```
Input: s = "Hello World"
Output: 5
```

```
Input: s = "   fly me   to   the moon  "
Output: 4
```

```
Input: s = "luffy is still joyboy"
Output: 6
```
