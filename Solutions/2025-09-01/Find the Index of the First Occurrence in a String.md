# Find the Index of the First Occurrence in a String

1.
 ```python
def strStr(haystack: str, needle: str) -> int:
    if not needle:
        return 0
    try:
        return haystack.index(needle)
    except ValueError:
        return -1

```
2.
 ```csharp
public class Solution {
    public int StrStr(string haystack, string needle) {
        if (string.IsNullOrEmpty(needle)) {
            return 0;
        }
        return haystack.IndexOf(needle);
    }
}
```
3. **Explanation (English)** The Python and C# solutions both utilize built-in string functions to find the index of the first occurrence of the needle string within the haystack string.  If the needle is empty, they return 0 as specified. If the needle is not found, a `ValueError` (Python) or `-1` (C#) is returned indicating that the needle is not present in the haystack.  The `IndexOf` method in C# and the `index` method in Python efficiently handle this string search operation.
	