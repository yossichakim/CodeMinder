# Remove Duplicates from Sorted Array

1.
 ```python
def removeDuplicates(nums):
    if not nums:
        return 0
    k = 1
    for i in range(1, len(nums)):
        if nums[i] != nums[i-1]:
            nums[k] = nums[i]
            k += 1
    return k

```
2.
 ```csharp
public int RemoveDuplicates(int[] nums) {
    if (nums.Length == 0) return 0;
    int k = 1;
    for (int i = 1; i < nums.Length; i++) {
        if (nums[i] != nums[i - 1]) {
            nums[k] = nums[i];
            k++;
        }
    }
    return k;
}
```
3. **Explanation (English)** The solutions use a two-pointer approach.  One pointer iterates through the array, and the other pointer (`k`) tracks the index for the next unique element. If a unique element is found, it's placed at the `k`th index, and `k` is incremented. The function returns `k`, representing the length of the array with duplicates removed.  The in-place modification directly alters the input array.
	