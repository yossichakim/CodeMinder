# Regular Expression Matching

1.
 ```python
def isMatch(s: str, p: str) -> bool:
    m, n = len(s), len(p)
    dp = [[False] * (n + 1) for _ in range(m + 1)]
    dp[0][0] = True
    for j in range(1, n + 1):
        if p[j - 1] == '*':
            dp[0][j] = dp[0][j - 2]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if p[j - 1] == '.' or p[j - 1] == s[i - 1]:
                dp[i][j] = dp[i - 1][j - 1]
            elif p[j - 1] == '*':
                dp[i][j] = dp[i][j - 2]
                if p[j - 2] == '.' or p[j - 2] == s[i - 1]:
                    dp[i][j] = dp[i][j] or dp[i - 1][j]
    return dp[m][n]

```
2.
 ```csharp
public class Solution {
    public bool IsMatch(string s, string p) {
        int m = s.Length;
        int n = p.Length;
        bool[,] dp = new bool[m + 1, n + 1];
        dp[0, 0] = true;
        for (int j = 1; j <= n; j++) {
            if (p[j - 1] == '*') {
                dp[0, j] = dp[0, j - 2];
            }
        }
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (p[j - 1] == '.' || p[j - 1] == s[i - 1]) {
                    dp[i, j] = dp[i - 1, j - 1];
                } else if (p[j - 1] == '*') {
                    dp[i, j] = dp[i, j - 2];
                    if (p[j - 2] == '.' || p[j - 2] == s[i - 1]) {
                        dp[i, j] = dp[i, j] || dp[i - 1, j];
                    }
                }
            }
        }
        return dp[m, n];
    }
}
```
3. **Explanation (English)** The solution uses dynamic programming to build a table where `dp[i][j]` represents whether the first `i` characters of `s` match the first `j` characters of `p`.  The table is filled iteratively, considering cases for literal characters, '.' (wildcard), and '*' (zero or more repetitions). The final result is found at `dp[m][n]`, where `m` and `n` are the lengths of `s` and `p` respectively.  The algorithm handles edge cases such as empty strings and patterns efficiently.
	