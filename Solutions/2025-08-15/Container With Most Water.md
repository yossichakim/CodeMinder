# Container With Most Water

1.
 ```python
def maxArea(height):
    l, r = 0, len(height) - 1
    max_area = 0
    while l < r:
        area = min(height[l], height[r]) * (r - l)
        max_area = max(max_area, area)
        if height[l] < height[r]:
            l += 1
        else:
            r -= 1
    return max_area
```
2.
 ```csharp
public class Solution {
    public int MaxArea(int[] height) {
        int l = 0, r = height.Length - 1;
        int maxArea = 0;
        while (l < r) {
            int area = Math.Min(height[l], height[r]) * (r - l);
            maxArea = Math.Max(maxArea, area);
            if (height[l] < height[r]) {
                l++;
            } else {
                r--;
            }
        }
        return maxArea;
    }
}
```
3. **Explanation (English)** The algorithm uses two pointers, one at the beginning and one at the end of the array. It calculates the area formed by the two lines and updates the maximum area. Then it moves the pointer pointing to the shorter line inward. This process continues until the pointers cross, efficiently finding the maximum area that can be contained between two lines.  The time complexity is O(n).
	