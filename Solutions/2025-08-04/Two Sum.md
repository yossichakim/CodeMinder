# Two Sum

1.
 ```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_map = {}  # Create a dictionary to store numbers and their indices
        for i, num in enumerate(nums):
            complement = target - num
            if complement in num_map:
                return [num_map[complement], i]  # Return indices if complement found
            num_map[num] = i  # Store number and its index

```
2.
 ```csharp
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        Dictionary<int, int> numMap = new Dictionary<int, int>();
        for (int i = 0; i < nums.Length; i++) {
            int complement = target - nums[i];
            if (numMap.ContainsKey(complement)) {
                return new int[] { numMap[complement], i };
            }
            numMap[nums[i]] = i;
        }
        return new int[0]; // Should not reach here if there's a solution
    }
}
```
3. **Explanation (English)** The solution uses a hash map (dictionary) to store each number and its index.  It iterates through the array, checking if the complement (target - current number) exists in the map. If it does, the indices are returned. Otherwise, the current number and its index are added to the map. This approach provides an efficient O(n) time complexity.
	