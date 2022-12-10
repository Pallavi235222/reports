# 024 Swap Nodes in Pairs

* * *
``Problem Statement``
  
<p>
Given a linked list, swap every two adjacent nodes and return its head. You must solve the problem without modifying the values in the list's nodes (i.e., only nodes themselves may be changed.)
</p>

***

`Solution :`

```
# 
class Solution(object):
    def swapPairs(self, head):
        dummyHead = ListNode(-1)
        dummyHead.next = head
        prev, p = dummyHead, head
        while p != None and p.next != None:
            q, r = p.next, p.next.next
            prev.next = q
            q.next = p
            p.next = r
            prev = p
            p = r
        return dummyHead.next
#
```

`Output:`

```
Input: head = [1,2,3,4]
Output: [2,1,4,3]
```

```
Input: head = []
Output: []
```

```
Input: head = [1]
Output: [1]
```
