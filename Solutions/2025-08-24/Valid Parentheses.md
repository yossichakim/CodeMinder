# Valid Parentheses

1.
 ```python
def isValid(s: str) -> bool:
    stack = []
    mapping = {')': '(', '}': '{', ']': '['}
    for char in s:
        if char in mapping:
            top_element = stack.pop() if stack else '#'
            if mapping[char] != top_element:
                return False
        else:
            stack.append(char)
    return not stack

```
2.
 ```csharp
using System;
using System.Collections.Generic;

public class Solution {
    public bool IsValid(string s) {
        Stack<char> stack = new Stack<char>();
        Dictionary<char, char> mapping = new Dictionary<char, char>() { { ')', '(' }, { '}', '{' }, { ']', '[' } };
        foreach (char c in s) {
            if (mapping.ContainsKey(c)) {
                char top = stack.Count > 0 ? stack.Pop() : '#';
                if (mapping[c] != top) return false;
            } else {
                stack.Push(c);
            }
        }
        return stack.Count == 0;
    }
}
```
3. **Explanation (English)** The solutions use a stack to track opening parentheses.  When a closing parenthesis is encountered, it's checked against the top of the stack. If they match, the opening parenthesis is popped; otherwise, it's invalid. Finally, an empty stack signifies a valid string.  The `mapping` dictionary efficiently provides the corresponding opening parenthesis for each closing one.
	