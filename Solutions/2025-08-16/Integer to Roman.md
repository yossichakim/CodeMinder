# Integer to Roman

1.
 ```python
def intToRoman(num: int) -> str:
    values = [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1]
    roman = ["M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"]
    result = ""
    i = 0
    while num > 0:
        for _ in range(num // values[i]):
            result += roman[i]
            num -= values[i]
        i += 1
    return result

```
2.
 ```csharp
public class Solution {
    public string IntToRoman(int num) {
        int[] values = {1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};
        string[] roman = {"M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"};
        string result = "";
        int i = 0;
        while (num > 0) {
            for (int j = 0; j < num / values[i]; ++j) {
                result += roman[i];
                num -= values[i];
            }
            i++;
        }
        return result;
    }
}
```
3. **Explanation (English)** The solution uses two arrays: one for integer values (1, 4, 5, 9, etc.) and another for their corresponding Roman numerals.  It iterates through the integer values, subtracting them from the input number as many times as possible and appending the corresponding Roman numeral to the result string. This efficiently handles both standard and subtractive Roman numeral combinations. The process continues until the input number is reduced to zero.
	