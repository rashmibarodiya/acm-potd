# House Robber (Memoization - Java)

## Description
Finds the maximum amount of money that can be robbed without robbing two adjacent houses.

## Approach
- Use recursion with memoization
- At each index:
  - Rob current house → move to `i + 2`
  - Skip current house → move to `i + 1`
- Store results in DP array to avoid recomputation

## Complexity
- Time: O(n)  
- Space: O(n)

## Code
```java
import java.util.*;

class Solution {
    int[] t = new int[101];
    int n;

    public int solve(int[] nums, int i){
        if(i >= n) return 0;

        if(t[i] != -1) return t[i];

        int robbed = nums[i] + solve(nums, i + 2);
        int notRob = solve(nums, i + 1);

        t[i] = Math.max(robbed, notRob);
        return t[i];
    }

    public int rob(int[] nums) {
        n = nums.length;
        Arrays.fill(t, -1);
        return solve(nums, 0);
    }
}
```
<img width="1916" height="1032" alt="image" src="https://github.com/user-attachments/assets/7a223fe8-f73f-4cbc-b31d-086ed491318f" />
