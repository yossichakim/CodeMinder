# Remove Element

1.
 ```python
def removeElement(nums, val):
    k = 0
    for i in range(len(nums)):
        if nums[i] != val:
            nums[k] = nums[i]
            k += 1
    return k
```

2.
 ```csharp
public int RemoveElement(int[] nums, int val) {
    int k = 0;
    for (int i = 0; i < nums.Length; i++) {
        if (nums[i] != val) {
            nums[k] = nums[i];
            k++;
        }
    }
    return k;
}
```

3. **Explanation (English)** The solutions use a two-pointer approach.  The `k` pointer tracks the index for elements to keep. The loop iterates through the array; if an element is not equal to the target value (`val`), it's placed at index `k`, and `k` is incremented. The function returns `k`, representing the new length of the array without the target value.  The in-place modification ensures efficiency.
	