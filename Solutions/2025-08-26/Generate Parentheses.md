# Generate Parentheses

1.
 ```python
def generateParenthesis(n: int) -> list[str]:
    result = []
    def backtrack(s='', left=0, right=0):
        if len(s) == 2 * n:
            result.append(s)
            return
        if left < n:
            backtrack(s + '(', left + 1, right)
        if right < left:
            backtrack(s + ')', left, right + 1)
    backtrack()
    return result

```
2.
 ```csharp
using System.Collections.Generic;

public class Solution {
    public IList<string> GenerateParenthesis(int n) {
        IList<string> result = new List<string>();
        Backtrack(result, "", 0, 0, n);
        return result;
    }

    private void Backtrack(IList<string> result, string current, int open, int close, int n) {
        if (current.Length == 2 * n) {
            result.Add(current);
            return;
        }
        if (open < n) {
            Backtrack(result, current + "(", open + 1, close, n);
        }
        if (close < open) {
            Backtrack(result, current + ")", open, close + 1, n);
        }
    }
}
```
3. **Explanation (English)** The solution uses backtracking to explore all possible combinations of parentheses.  It maintains counts of open and closed parentheses, ensuring that the number of closed parentheses never exceeds the number of open ones.  The base case is when the string length reaches 2n, indicating a valid combination. The function recursively adds '(' if open < n and ')' if close < open, exploring all valid paths.
	