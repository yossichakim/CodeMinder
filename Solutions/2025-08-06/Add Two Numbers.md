# Add Two Numbers

1.
 ```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def addTwoNumbers(l1, l2):
    dummy = ListNode(0)  # Create a dummy node to simplify the head handling
    current = dummy
    carry = 0

    while l1 or l2 or carry:
        val1 = l1.val if l1 else 0
        val2 = l2.val if l2 else 0
        sum_vals = val1 + val2 + carry
        carry = sum_vals // 10
        current.next = ListNode(sum_vals % 10)
        current = current.next

        l1 = l1.next if l1 else None
        l2 = l2.next if l2 else None

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
    public ListNode AddTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode current = dummy;
        int carry = 0;

        while (l1 != null || l2 != null || carry != 0) {
            int val1 = l1?.val ?? 0;
            int val2 = l2?.val ?? 0;
            int sum = val1 + val2 + carry;
            carry = sum / 10;
            current.next = new ListNode(sum % 10);
            current = current.next;
            l1 = l1?.next;
            l2 = l2?.next;
        }
        return dummy.next;
    }
}
```
3. **Explanation (English)** The solutions iterate through linked lists `l1` and `l2`, summing corresponding digits and handling carry-over. A dummy node simplifies head management.  The loop continues until both lists are processed and there's no carry remaining. The function returns the head of the resulting linked list.  The C# solution uses the null-conditional operator (`?.`) for concise null checks.
	