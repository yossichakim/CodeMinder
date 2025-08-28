# Swap Nodes in Pairs

1.
 ```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def swapPairs(head):
    dummy = ListNode(0, head)
    prev = dummy
    curr = head

    while curr and curr.next:
        first = curr
        second = curr.next
        
        prev.next = second
        first.next = second.next
        second.next = first
        
        prev = first
        curr = first.next
    return dummy.next

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
    public ListNode SwapPairs(ListNode head) {
        ListNode dummy = new ListNode(0, head);
        ListNode prev = dummy;
        ListNode curr = head;

        while (curr != null && curr.next != null) {
            ListNode first = curr;
            ListNode second = curr.next;

            prev.next = second;
            first.next = second.next;
            second.next = first;

            prev = first;
            curr = first.next;
        }
        return dummy.next;
    }
}
```
3. **Explanation (English)** – The solution iteratively swaps pairs of nodes in a linked list.  It uses a dummy node to simplify the handling of the head. The `while` loop continues as long as there are at least two nodes remaining. Inside the loop, pointers are manipulated to swap the nodes and update the `prev` and `curr` pointers for the next iteration.  Finally, the dummy node is bypassed to return the new head.
	