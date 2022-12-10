# 019 Remove Nth Node From End of List

* * *
``Problem Statement``
  
<p>
Given the head of a linked list, remove the nth node from the end of the list and return its head.
</p>

***

`Solution :`

```
# 
class Solution(object):
    def removeNthFromEnd(self,head, n):
        if head is None:
            return None
        slow = fast = head
        for i in range(n):
            fast = fast.next
        if fast is None:
            head = head.next
            return head
        while fast.next is not None:
            fast = fast.next
            slow = slow.next
        curr = slow.next
        slow.next = curr.next
        return head
#
```

`Output:`

```
Input: head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]
```

```
Input: head =[1], n =1
Output: []
```

```
Input: head = [1,2], n = 1
Output: [1]
```
