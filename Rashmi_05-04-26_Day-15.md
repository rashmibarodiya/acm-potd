# Valid Parentheses (Java)

## Description
Checks if a string of brackets is valid. A string is valid if brackets are closed in the correct order.

## Approach
- Use a stack to track opening brackets
- Push opening brackets onto stack
- For closing brackets, check top of stack and pop if matching
- If stack is empty at the end → valid

## Complexity
- Time: O(n)
- Space: O(n)

## Code
```java
import java.util.*;

class Solution {
    public boolean isValid(String s) {
        Stack<Character> st = new Stack<>();

        st.push(s.charAt(0));

        for(int i = 1; i < s.length(); i++){
            if(!st.isEmpty()){
                int diff = (s.charAt(i) - ' ') - (st.peek() - ' ');
                if(diff > 0 && diff < 3) st.pop();
                else st.push(s.charAt(i));
            } else {
                st.push(s.charAt(i));
            }
        }



        return st.isEmpty();
    }
}
```

<img width="1910" height="1025" alt="image" src="https://github.com/user-attachments/assets/305668df-f71d-41de-a4d9-499030e7a4b0" />
