# Letter Combinations of a Phone Number

1.
 ```python
class Solution:
    def letterCombinations(self, digits: str) -> List[str]:
        if not digits:
            return []
        mapping = {'2': 'abc', '3': 'def', '4': 'ghi', '5': 'jkl', '6': 'mno', '7': 'pqrs', '8': 'tuv', '9': 'wxyz'}
        result = ['']
        for digit in digits:
            new_result = []
            for combo in result:
                for char in mapping[digit]:
                    new_result.append(combo + char)
            result = new_result
        return result

```
2.
 ```csharp
using System.Collections.Generic;

public class Solution {
    public IList<string> LetterCombinations(string digits) {
        if (string.IsNullOrEmpty(digits)) return new List<string>();
        Dictionary<char, string> mapping = new Dictionary<char, string>() {
            {'2', "abc"}, {'3', "def"}, {'4', "ghi"}, {'5', "jkl"},
            {'6', "mno"}, {'7', "pqrs"}, {'8', "tuv"}, {'9', "wxyz"}
        };
        List<string> result = new List<string>() { "" };
        foreach (char digit in digits) {
            List<string> newResult = new List<string>();
            foreach (string combo in result) {
                foreach (char c in mapping[digit]) {
                    newResult.Add(combo + c);
                }
            }
            result = newResult;
        }
        return result;
    }
}
```
3. **Explanation (English)** The solutions use a recursive backtracking approach or iterative approach.  They iterate through the digits, mapping each digit to its corresponding letters.  At each digit, they generate new combinations by appending each letter to the existing combinations from the previous digits. Finally,  the function returns a list of all possible letter combinations.
	