# Median of Two Sorted Arrays

1.
 ```python
import heapq

def findMedianSortedArrays(nums1, nums2):
    merged = heapq.merge(nums1, nums2)
    merged_list = list(merged)
    n = len(merged_list)
    if n % 2 == 0:
        mid1 = merged_list[n // 2 - 1]
        mid2 = merged_list[n // 2]
        median = (mid1 + mid2) / 2
    else:
        median = merged_list[n // 2]
    return median

```
2.
 ```csharp
using System;
using System.Collections.Generic;
using System.Linq;

public class Solution {
    public double FindMedianSortedArrays(int[] nums1, int[] nums2) {
        List<int> merged = nums1.Concat(nums2).OrderBy(x => x).ToList();
        int n = merged.Count;
        if (n % 2 == 0) {
            return (double)(merged[n / 2 - 1] + merged[n / 2]) / 2;
        } else {
            return merged[n / 2];
        }
    }
}
```
3. **Explanation (English)** The solutions merge the two sorted input arrays using Python's `heapq.merge` or C#'s `Concat` and `OrderBy`.  Then, they determine the median based on whether the merged array's length is even or odd. If even, the median is the average of the two middle elements; otherwise, it's the middle element.  Both solutions efficiently find the median without needing to sort the entire merged array explicitly in the Python case, leveraging the efficiency of heapq.merge.
	