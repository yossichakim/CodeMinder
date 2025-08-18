# Longest Common Prefix

1.
 ```python
def longestCommonPrefix(strs):
    if not strs:
        return ""
    prefix = strs[0]
    for s in strs[1:]:
        i = 0
        while i < len(prefix) and i < len(s) and prefix[i] == s[i]:
            i += 1
        prefix = prefix[:i]
    return prefix
```
2.
 ```csharp
public string LongestCommonPrefix(string[] strs) {
    if (strs == null || strs.Length == 0) return "";
    string prefix = strs[0];
    for (int i = 1; i < strs.Length; i++) {
        while (strs[i].IndexOf(prefix) != 0) {
            prefix = prefix.Substring(0, prefix.Length - 1);
            if (prefix.Length == 0) return "";
        }
    }
    return prefix;
}
```
3. **Explanation (English)** The Python and C# solutions both iterate through the input string array.  They compare each string to a running `prefix`, shortening the `prefix` if a mismatch is found.  The process continues until either a common prefix is found for all strings or the `prefix` becomes empty, indicating no common prefix. The final `prefix` is returned as the result.
	