# String to Integer (atoi)

1.
 ```python
def myAtoi(s: str) -> int:
    s = s.strip()
    if not s:
        return 0
    sign = -1 if s[0] == '-' else 1
    if s[0] in ['-', '+']:
        s = s[1:]
    result = 0
    for char in s:
        if not char.isdigit():
            break
        result = result * 10 + int(char)
    result *= sign
    result = max(-2**31, min(result, 2**31 - 1))
    return result

```
2.
 ```csharp
public class Solution {
    public int MyAtoi(string s) {
        s = s.Trim();
        if (s.Length == 0) return 0;
        int sign = 1;
        if (s[0] == '-') {
            sign = -1;
            s = s.Substring(1);
        } else if (s[0] == '+') {
            s = s.Substring(1);
        }
        long result = 0;
        foreach (char c in s) {
            if (!char.IsDigit(c)) break;
            result = result * 10 + (c - '0');
            if (result * sign > int.MaxValue) return int.MaxValue;
            if (result * sign < int.MinValue) return int.MinValue;
        }
        return (int)(result * sign);
    }
}
```
3. **Explanation (English)** The solution trims leading/trailing whitespace, handles +/- signs, and iterates through the string, converting digits to an integer.  It checks for integer overflow, ensuring the result stays within the 32-bit signed integer range.  Finally, it returns the appropriately signed integer.
	