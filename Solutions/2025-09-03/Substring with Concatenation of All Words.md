# Substring with Concatenation of All Words

1.
 ```python
def findSubstring(s, words):
    word_len = len(words[0])
    total_len = word_len * len(words)
    result = []
    word_count = {}
    for word in words:
        word_count[word] = word_count.get(word, 0) + 1

    for i in range(len(s) - total_len + 1):
        seen = {}
        j = 0
        while j < len(words):
            word = s[i + j * word_len:i + (j + 1) * word_len]
            if word not in word_count:
                break
            seen[word] = seen.get(word, 0) + 1
            if seen[word] > word_count[word]:
                break
            j += 1
        if j == len(words):
            result.append(i)
    return result

```
2.
 ```csharp
using System;
using System.Collections.Generic;

public class Solution {
    public IList<int> FindSubstring(string s, string[] words) {
        int wordLen = words[0].Length;
        int totalLen = wordLen * words.Length;
        IList<int> result = new List<int>();
        Dictionary<string, int> wordCount = new Dictionary<string, int>();
        foreach (string word in words) {
            wordCount[word] = wordCount.ContainsKey(word) ? wordCount[word] + 1 : 1;
        }

        for (int i = 0; i <= s.Length - totalLen; i++) {
            Dictionary<string, int> seen = new Dictionary<string, int>();
            int j = 0;
            while (j < words.Length) {
                string word = s.Substring(i + j * wordLen, wordLen);
                if (!wordCount.ContainsKey(word)) break;
                seen[word] = seen.ContainsKey(word) ? seen[word] + 1 : 1;
                if (seen[word] > wordCount[word]) break;
                j++;
            }
            if (j == words.Length) result.Add(i);
        }
        return result;
    }
}
```
3. **Explanation (English)** The solution uses a sliding window approach.  It iterates through the string, maintaining a dictionary to count the occurrences of words within the window. If the window contains all words from the input list with the correct counts, the starting index is added to the result. The window size is fixed to the total length of all words.  The algorithm efficiently handles potential duplicates in the `words` array.
	