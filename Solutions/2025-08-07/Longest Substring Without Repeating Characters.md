# Longest Substring Without Repeating Characters

1.
 ```python
def lengthOfLongestSubstring(s: str) -> int:
    n = len(s)
    ans = 0
    # mp stores the current index of a character
    mp = {}

    i = 0
    for j in range(n):
        if s[j] in mp:
            i = max(mp[s[j]], i)

        ans = max(ans, j - i + 1)
        mp[s[j]] = j + 1

    return ans
```
2.
 ```csharp
public class Solution {
    public int LengthOfLongestSubstring(string s) {
        int n = s.Length;
        int ans = 0;
        Dictionary<char, int> map = new Dictionary<char, int>();
        int i = 0;
        for (int j = 0; j < n; j++) {
            if (map.ContainsKey(s[j])) {
                i = Math.Max(map[s[j]], i);
            }
            ans = Math.Max(ans, j - i + 1);
            map[s[j]] = j + 1;
        }
        return ans;
    }
}
```
3. **Explanation (English)** The solution uses a sliding window approach.  A dictionary `mp` (or `map`) tracks the last seen index of each character. The window expands as long as no repeating character is found. When a repeat is found, the window's left boundary is moved to the right of the repeated character's last occurrence.  The maximum window size is tracked and returned as the result.
	