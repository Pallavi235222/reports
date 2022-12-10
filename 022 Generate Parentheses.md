# 022 Generate Parentheses

* * *
``Problem Statement``
  
<p>
Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.
</p>

***

`Solution :`

```
# 
class Solution(object):
    def generateParenthesis(self, n):
        if n == 1:
            return ['()']
        last_list = self.generateParenthesis(n-1)
        res = []
        for t in last_list:
            curr = t +')'
            for index in range(len(curr)):
                if curr[index] == ')':
                    res.append(curr[:index] + '(' + curr[index:])
        return lis
#
```

`Output:`

```
Input: n = 3
Output: ["(()())","()(())","()()()","((()))","(())()"]
```

```
Input: n =1
Output: ["()"]
```


