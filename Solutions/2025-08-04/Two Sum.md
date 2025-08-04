# Two Sum

1.
 ```python
class Solution:
    def twoSum(self, nums: list[int], target: int) -> list[int]:
        num_map = {}  # Create a dictionary to store numbers and their indices
        for i, num in enumerate(nums):
            complement = target - num
            if complement in num_map:
                return [num_map[complement], i]  # Return indices if complement found
            num_map[num] = i  # Store the number and its index
        return []  # Return empty list if no solution found

```
2.
 ```csharp
using System.Collections.Generic;

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
        return new int[0]; // Return empty array if no solution
    }
}
```
3. **Explanation (English)** The solution uses a dictionary (hash map) to store each number and its index.  It iterates through the input array, checking if the complement (target - current number) exists in the dictionary. If found, it returns the indices of the complement and the current number. Otherwise, it adds the current number and its index to the dictionary.  This approach provides an efficient O(n) time complexity.
	