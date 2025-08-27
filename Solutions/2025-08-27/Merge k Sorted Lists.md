# Merge k Sorted Lists

1.
 ```python
import heapq

def mergeKLists(lists):
    heap = []
    for i, lst in enumerate(lists):
        if lst:
            heapq.heappush(heap, (lst.val, i, lst))

    dummy = ListNode(0)
    curr = dummy

    while heap:
        val, i, node = heapq.heappop(heap)
        curr.next = node
        curr = curr.next
        if node.next:
            heapq.heappush(heap, (node.next.val, i, node.next))

    return dummy.next
```
2.
 ```csharp
using System.Collections.Generic;

public class Solution {
    public ListNode MergeKLists(ListNode[] lists) {
        PriorityQueue<(int, int, ListNode), (int, int, ListNode)> heap = new PriorityQueue<(int, int, ListNode), (int, int, ListNode)>();
        for (int i = 0; i < lists.Length; i++) {
            if (lists[i] != null) {
                heap.Enqueue((lists[i].val, i, lists[i]), (lists[i].val, i, lists[i]));
            }
        }

        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;

        while (heap.Count > 0) {
            (int val, int i, ListNode node) = heap.Dequeue();
            curr.next = node;
            curr = curr.next;
            if (node.next != null) {
                heap.Enqueue((node.next.val, i, node.next), (node.next.val, i, node.next));
            }
        }
        return dummy.next;
    }
}
```
3. **Explanation (English)** The solution uses a min-heap to efficiently merge k sorted lists.  The heap stores (value, list index, node) tuples, allowing us to always access the smallest element across all lists.  We iteratively extract the minimum element, add it to the result, and push the next element from the same list onto the heap.  Finally, we return the merged list.  The use of a priority queue (heap) ensures logarithmic time complexity for each insertion and extraction.
	