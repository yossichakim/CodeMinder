# Two Sum

1.
 ```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_map = {}
        for index, num in enumerate(nums):
            complement = target - num
            if complement in num_map:
                return [num_map[complement], index]
            num_map[num] = index
        return []

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
        return new int[0]; // Return empty array if no solution found
    }
}
```
3. **Explanation (English)** The solution uses a hash map (dictionary in C#) to store each number and its index.  It iterates through the input array, checking if the complement (target - current number) exists in the map. If found, it returns the indices of the complement and the current number. Otherwise, it adds the current number and its index to the map and continues.  If no solution is found, an empty array is returned.
	