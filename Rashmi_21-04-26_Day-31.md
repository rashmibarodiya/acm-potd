# Climbing Stairs (C++)

## Description
Finds the number of distinct ways to climb `n` stairs where you can take 1 or 2 steps at a time.

## Approach
- This follows Fibonacci pattern:
  - ways(n) = ways(n-1) + ways(n-2)
- Use two variables to store previous results
- Iteratively compute the result

## Complexity
- Time: O(n)  
- Space: O(1)

## Code
```cpp
class Solution {
public:
    int climbStairs(int n) {
        if(n == 1 || n == 2) return n;

        int prev2 = 1;
        int prev1 = 2;
        int res = prev2 + prev1;

        for(int i = 3; i <= n; i++){
            res = prev2 + prev1;
            prev2 = prev1;
            prev1 = res;
        }

        return res;
    }
};
```
<img width="1917" height="1036" alt="image" src="https://github.com/user-attachments/assets/5e9a4fc4-43b1-4e32-8fbc-a340a32b1bc2" />
