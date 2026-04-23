# Min Cost Climbing Stairs (Java)

## Description
Finds the minimum cost to reach the top of the staircase. You can climb either 1 or 2 steps at a time.

## Approach
- Use bottom-up DP
- `dp[i]` stores minimum cost to reach step `i`
- Transition:
  - `dp[i] = cost[i] + min(dp[i-1], dp[i-2])`
- Final answer:
  - `min(dp[n-1], dp[n-2])`

## Complexity
- Time: O(n)  
- Space: O(n)

## Code
```java
class Solution {
    public int minCostClimbingStairs(int[] cost) {
        int n = cost.length;
        int[] dp = new int[n];

        for (int i = 0; i < n; i++) {
            if (i < 2)
                dp[i] = cost[i];
            else
                dp[i] = cost[i] + Math.min(dp[i - 1], dp[i - 2]);
        }

        return Math.min(dp[n - 1], dp[n - 2]);
    }
}
```
<img width="1919" height="1035" alt="image" src="https://github.com/user-attachments/assets/2a257877-a713-4973-a699-da5a1765c582" />
