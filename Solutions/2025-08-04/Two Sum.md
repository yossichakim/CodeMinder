# Two Sum

1.
 ```python
def twoSum(nums, target):
    num_map = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in num_map:
            return [num_map[complement], i]
        num_map[num] = i
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
3. **Explanation (English)** The solution uses a hash map (dictionary in C#) to store each number and its index.  It iterates through the input array, checking if the complement (target - current number) exists in the map. If it does, the indices are returned. Otherwise, the current number and its index are added to the map.  The time complexity is O(n) because of the single pass through the array.
	