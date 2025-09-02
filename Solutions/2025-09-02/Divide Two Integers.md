# Divide Two Integers

1.
 ```python
def divide(dividend: int, divisor: int) -> int:
    sign = -1 if (dividend < 0) ^ (divisor < 0) else 1
    dividend = abs(dividend)
    divisor = abs(divisor)
    quotient = 0
    temp = 0
    for i in range(31, -1, -1):
        if (temp + (divisor << i)) <= dividend:
            temp += divisor << i
            quotient |= 1 << i
    result = sign * quotient
    return min(max(result, -2147483648), 2147483647)

```
2.
 ```csharp
public class Solution {
    public int Divide(int dividend, int divisor) {
        long sign = ((dividend < 0) ^ (divisor < 0)) ? -1 : 1;
        long dividendL = Math.Abs((long)dividend);
        long divisorL = Math.Abs((long)divisor);
        long quotient = 0;
        long temp = 0;
        for (int i = 31; i >= 0; i--) {
            if ((temp + (divisorL << i)) <= dividendL) {
                temp += divisorL << i;
                quotient |= 1L << i;
            }
        }
        long result = sign * quotient;
        return (int)Math.Min(Math.Max(result, -2147483648), 2147483647);
    }
}
```
3. **Explanation (English)** The solution uses bit manipulation for efficient division. It handles signs separately and iteratively checks if multiples of the divisor (left-shifted) can be subtracted from the dividend.  The quotient is built bit by bit, and the result is adjusted to account for potential overflow.  Finally, the result is clamped to the 32-bit integer range.
	