# Reverse Nodes in k-Group

1.
 ```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def reverseKGroup(head, k):
    dummy = ListNode(0, head)
    group_prev = dummy
    while True:
        kth = getKth(group_prev, k)
        if not kth:
            break
        group_next = kth.next
        prev, curr = kth.next, group_prev.next
        while curr != group_next:
            next_temp = curr.next
            curr.next = prev
            prev = curr
            curr = next_temp
        group_prev.next = prev
        group_prev = kth
    return dummy.next

def getKth(curr, k):
    while curr and k > 0:
        curr = curr.next
        k -= 1
    return curr
```
2.
 ```csharp
public class ListNode {
    public int val;
    public ListNode next;
    public ListNode(int val = 0, ListNode next = null) {
        this.val = val;
        this.next = next;
    }
}
public class Solution {
    public ListNode ReverseKGroup(ListNode head, int k) {
        ListNode dummy = new ListNode(0, head);
        ListNode groupPrev = dummy;
        while (true) {
            ListNode kth = GetKth(groupPrev, k);
            if (kth == null) break;
            ListNode groupNext = kth.next;
            ListNode prev = groupNext, curr = groupPrev.next;
            while (curr != groupNext) {
                ListNode nextTemp = curr.next;
                curr.next = prev;
                prev = curr;
                curr = nextTemp;
            }
            groupPrev.next = prev;
            groupPrev = kth;
        }
        return dummy.next;
    }
    private ListNode GetKth(ListNode curr, int k) {
        while (curr != null && k > 0) {
            curr = curr.next;
            k--;
        }
        return curr;
    }
}
```
3. **Explanation (English)** The solution iteratively reverses groups of k nodes in a linked list.  It uses helper functions `getKth` to find the k-th node and efficiently reverses the group using three pointers: `prev`, `curr`, and `nextTemp`. The reversed group is then linked back to the previous group, and the process repeats until the end of the list.  A dummy node simplifies handling the head of the list.
	