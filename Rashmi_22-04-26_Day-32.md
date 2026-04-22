# Pascal's Triangle (Java)

## Description
Generates the first `r` rows of Pascal's Triangle.

## Approach
- Start with first row `[1]`
- For each next row:
  - First and last elements are `1`
  - Middle elements = sum of two elements from previous row
- Build row by row

## Complexity
- Time: O(r²)  
- Space: O(r²)

## Code
```java
import java.util.*;

class Solution {
    public List<List<Integer>> generate(int r) {
        List<List<Integer>> ans = new ArrayList<>();
        ans.add(new ArrayList<>(List.of(1)));

        for(int i = 1; i < r; i++){
            List<Integer> l = new ArrayList<>();
            List<Integer> prev = ans.get(i - 1);

            l.add(1);

            for(int j = 0; j < i - 1; j++){
                l.add(prev.get(j) + prev.get(j + 1));
            }

            l.add(1);
            ans.add(l);
        }

        return ans;
    }
}
```
<img width="1915" height="1007" alt="image" src="https://github.com/user-attachments/assets/9aef9e54-b6bb-44fe-9627-8eb694b0ef3f" />
