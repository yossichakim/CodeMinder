# Longest Palindromic Substring

1.
 ```python
def longestPalindrome(s):
    n = len(s)
    if n < 2:
        return s
    
    start = 0
    max_len = 1
    
    for i in range(n):
        l, r = i, i
        while l >= 0 and r < n and s[l] == s[r]:
            if r - l + 1 > max_len:
                max_len = r - l + 1
                start = l
            l -= 1
            r += 1
        
        l, r = i, i + 1
        while l >= 0 and r < n and s[l] == s[r]:
            if r - l + 1 > max_len:
                max_len = r - l + 1
                start = l
            l -= 1
            r += 1
            
    return s[start:start + max_len]

```
2.
 ```csharp
public string LongestPalindrome(string s) {
    int n = s.Length;
    if (n < 2) return s;

    int start = 0;
    int maxLen = 1;

    for (int i = 0; i < n; i++) {
        int l = i, r = i;
        while (l >= 0 && r < n && s[l] == s[r]) {
            if (r - l + 1 > maxLen) {
                maxLen = r - l + 1;
                start = l;
            }
            l--;
            r++;
        }

        l = i;
        r = i + 1;
        while (l >= 0 && r < n && s[l] == s[r]) {
            if (r - l + 1 > maxLen) {
                maxLen = r - l + 1;
                start = l;
            }
            l--;
            r++;
        }
    }
    return s.Substring(start, maxLen);
}
```
3. **Explanation (English)** The solution uses a dynamic programming approach. It iterates through the string, expanding around each character to find the longest palindrome centered at that character.  Two loops handle both odd and even length palindromes. The `start` and `maxLen` variables track the starting index and length of the longest palindrome found so far.  The function then returns the substring representing the longest palindrome.
	