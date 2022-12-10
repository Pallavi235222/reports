# 025 Reverse Nodes in K-Group

* * *
``Problem Statement``
  
<p>
Given the head of a linked list, reverse the nodes of the list k at a time, and return the modified list.

k is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of k then left-out nodes, in the end, should remain as it is.

You may not alter the values in the list's nodes, only nodes themselves may be changed.

</p>

***

`Solution :`

```
# 
class Solution(object):
    def reverseKGroup(self, head, k):
        if head is None:
            return None
        index = 0
        lead, last = 0,0
        pos = head
        temp = ListNode(-1)
        temp.next = head
        head = temp
        start = head
        while pos is not None:
            if index % k == k - 1:
                last = pos.next
                start = self.reverseList(start,last)
                pos = start
            pos = pos.next
            index += 1
        return head.next
    def reverseList(self, head, end):
        pos = head.next
        last = end
        next_start = pos
        while pos != end:
            head.next = pos
            last_pos = pos
            pos = pos.next
            last_pos.next = last
            last = last_pos
        return next_start
#
```

`Output:`

```
Input: head = [1,2,3,4,5], k = 2
Output: [2,1,4,3,5]
```

```
Input: head = [1,2,3,4,5], k = 3
Output: [3,2,1,4,5]
```


