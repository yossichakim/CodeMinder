# Two Sum

1. ```python
def twoSum(nums, target):
    num_map = {}  # Create a dictionary to store numbers and their indices
    for i, num in enumerate(nums):
        complement = target - num
        if complement in num_map:
            return [num_map[complement], i]  # Return indices if complement is found
        num_map[num] = i  # Add number and its index to the dictionary
    return []  # Return empty list if no solution is found

```
2. ```csharp
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
        return new int[0]; // Return empty array if no solution is found
    }
}
```
3. **Explanation (English)** The solution uses a hash map (dictionary in Python, Dictionary in C#) to store each number and its index. It iterates through the input array; for each number, it checks if its complement (target - number) exists in the hash map. If it does, the indices of the two numbers are returned. Otherwise, the number and its index are added to the hash map.  This approach achieves a time complexity of O(n) because hash map lookups are typically O(1).	