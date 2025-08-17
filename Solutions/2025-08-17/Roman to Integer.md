# Roman to Integer

1.
 ```python
class Solution:
    def romanToInt(self, s: str) -> int:
        roman_map = {'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000}
        result = 0
        prev_value = 0
        for i in range(len(s) - 1, -1, -1):
            curr_value = roman_map[s[i]]
            if curr_value < prev_value:
                result -= curr_value
            else:
                result += curr_value
            prev_value = curr_value
        return result

```
2.
 ```csharp
public class Solution {
    public int RomanToInt(string s) {
        Dictionary<char, int> romanMap = new Dictionary<char, int>() {
            {'I', 1}, {'V', 5}, {'X', 10}, {'L', 50}, {'C', 100}, {'D', 500}, {'M', 1000}
        };
        int result = 0;
        int prevValue = 0;
        for (int i = s.Length - 1; i >= 0; i--) {
            int currValue = romanMap[s[i]];
            if (currValue < prevValue) {
                result -= currValue;
            } else {
                result += currValue;
            }
            prevValue = currValue;
        }
        return result;
    }
}
```
3. **Explanation (English)** The solution iterates through the Roman numeral string from right to left.  It uses a dictionary to map Roman numerals to their integer values.  If a smaller value precedes a larger value (e.g., "IV"), it subtracts the smaller value; otherwise, it adds the value to the result.  The final result is the integer representation of the Roman numeral.
	