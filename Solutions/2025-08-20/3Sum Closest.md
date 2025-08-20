# 3Sum Closest

1.
 ```python
def threeSumClosest(nums, target):
    nums.sort()
    closestSum = float('inf')

    for i in range(len(nums) - 2):
        left = i + 1
        right = len(nums) - 1

        while left < right:
            currentSum = nums[i] + nums[left] + nums[right]
            if abs(currentSum - target) < abs(closestSum - target):
                closestSum = currentSum
            if currentSum < target:
                left += 1
            elif currentSum > target:
                right -= 1
            else:
                return target  # Exact match found

    return closestSum
```
2.
 ```csharp
using System;
using System.Collections.Generic;
using System.Linq;

public class Solution {
    public int ThreeSumClosest(int[] nums, int target) {
        Array.Sort(nums);
        int closestSum = int.MaxValue;

        for (int i = 0; i < nums.Length - 2; i++) {
            int left = i + 1;
            int right = nums.Length - 1;

            while (left < right) {
                int currentSum = nums[i] + nums[left] + nums[right];
                if (Math.Abs(currentSum - target) < Math.Abs(closestSum - target)) {
                    closestSum = currentSum;
                }
                if (currentSum < target) {
                    left++;
                } else if (currentSum > target) {
                    right--;
                } else {
                    return target; // Exact match found
                }
            }
        }
        return closestSum;
    }
}
```
3. **Explanation (English)** The solution utilizes a three-pointer approach.  First, the input array is sorted. Then, using a three-pointer method (one pointer iterates through the array, two others point to the remaining elements) it finds the sum of three numbers that is closest to the target. The algorithm updates the `closestSum` variable as it iterates, ensuring that the closest sum is always tracked. Finally, the function returns this closest sum.
	