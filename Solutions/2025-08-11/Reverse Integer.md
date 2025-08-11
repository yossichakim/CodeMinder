# Reverse Integer

1.
 ```python
def reverse(x):
    sign = -1 if x < 0 else 1
    x = abs(x)
    reversed_x = 0
    while x > 0:
        pop = x % 10
        x //= 10
        reversed_x = reversed_x * 10 + pop
    reversed_x *= sign
    if reversed_x > 2**31 -1 or reversed_x < -2**31:
        return 0
    return reversed_x

```
2.
 ```csharp
public class Solution {
    public int Reverse(int x) {
        long reversed = 0;
        int sign = Math.Sign(x);
        x = Math.Abs(x);
        while(x > 0){
            reversed = reversed * 10 + x % 10;
            x /= 10;
        }
        reversed *= sign;

        if(reversed > int.MaxValue || reversed < int.MinValue){
            return 0;
        }
        return (int)reversed;
    }
}
```
3. **Explanation (English)** The solutions reverse an integer by repeatedly extracting the last digit using the modulo operator and building the reversed integer.  They handle negative numbers by tracking the sign separately.  Finally, they check for integer overflow before returning the result to prevent unexpected behavior.  A `long` is used in C# to temporarily store the reversed number before casting to `int` to avoid overflow during the reversal process.
	