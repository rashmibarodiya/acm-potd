# Make The String Great (Java)

## Description
Removes adjacent characters where the same letter appears in different cases (e.g., 'a' and 'A') until no such pairs remain.

## Approach
- Use a stack to process characters
- If current character and top differ by 32 (ASCII case difference), remove top
- Otherwise, push current character
- Build result from stack

## Complexity
- Time: O(n)  
- Space: O(n)

## Code
```java
import java.util.*;

class Solution {
    public String makeGood(String s) {
        Stack<Character> stack = new Stack<>();
        
        for (char c : s.toCharArray()) {
            if (!stack.isEmpty() && Math.abs(c - stack.peek()) == 32) {
                stack.pop();
            } else {
                stack.push(c);
            }
        }
        
        StringBuilder result = new StringBuilder();
        while (!stack.isEmpty()) {
            result.insert(0, stack.pop());
        }
        
        return result.toString();
    }
}
```
<img width="1919" height="1033" alt="image" src="https://github.com/user-attachments/assets/41054cab-1830-42cc-a24d-8d3518462cd0" />
