# Palindrome Number

1.
 ```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0:
            return False
        original = x
        reversed_x = 0
        while x > 0:
            reversed_x = reversed_x * 10 + x % 10
            x //= 10
        return original == reversed_x

```
2.
 ```csharp
public class Solution {
    public bool IsPalindrome(int x) {
        if (x < 0) return false;
        string s = x.ToString();
        string reversed_s = new string(s.Reverse().ToArray());
        return s == reversed_s;
    }
}
```
3. **Explanation (English)** The Python solution efficiently reverses the integer and compares it to the original.  The C# solution converts the integer to a string, reverses the string, and compares the reversed string to the original string. Both solutions handle negative numbers, which are not palindromes.  The time complexity for both is O(log10(n)) for the Python and O(n) for the C# approach where n is the number of digits.
	