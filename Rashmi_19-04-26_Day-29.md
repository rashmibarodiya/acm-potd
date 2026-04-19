# Fibonacci Number (Memoization - Java)

## Description
Computes the nth Fibonacci number using recursion with memoization.

## Approach
- Use a dp array to store computed results
- Base cases:
  - fib(0) = 0
  - fib(1) = 1
- For other values:
  - fib(n) = fib(n-1) + fib(n-2)
- Store results in dp to avoid recomputation

## Complexity
- Time: O(n)  
- Space: O(n)

## Code
```java
import java.util.*;

class Solution {
    int[] dp = new int[31];
    {
        Arrays.fill(dp, -1);
    }

    public int fib(int n) {
        if(dp[n] != -1) return dp[n];
        if(n == 0 || n == 1) return n;

        return dp[n] = fib(n - 1) + fib(n - 2);
    }
}
```
<img width="1918" height="1024" alt="image" src="https://github.com/user-attachments/assets/5f7e9b50-26ae-4b5a-b674-ad3761147c50" />
