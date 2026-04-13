# Find the Town Judge (Java)

## Description
Finds the town judge. The judge trusts nobody and is trusted by all other `n - 1` people.

## Approach
- Use a score array:
  - Decrease score for trusting someone
  - Increase score for being trusted
- Judge will have score = `n - 1`

## Complexity
- Time: O(n + t)  
- Space: O(n)

## Code
```java
class Solution {
    public int findJudge(int n, int[][] trust) {
        int[] score = new int[n + 1];

        for(int[] ar : trust){
            score[ar[0]]--; // trusts someone
            score[ar[1]]++; // trusted by someone
        }

        for(int i = 1; i <= n; i++){
            if(score[i] == n - 1) return i;
        }

        return -1;
    }
}
```
<img width="1918" height="1036" alt="image" src="https://github.com/user-attachments/assets/3b8de450-03fa-410e-bea5-fb4b12c35ac8" />
