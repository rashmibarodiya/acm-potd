# Backspace String Compare (Java)

## Description
Compares two strings after processing backspace characters (`#`). A `#` removes the previous character.

## Approach
- Use a stack to simulate typing
- For each string:
  - Push characters
  - On `#`, pop if not empty
- Build final strings and compare

## Complexity
- Time: O(n + m)  
- Space: O(n + m)

## Code
```java
import java.util.*;

class Solution {
    public boolean backspaceCompare(String s, String t) {
        Stack<Character> st = new Stack<>();

        for (int i = 0; i < s.length(); i++) {
            if (s.charAt(i) == '#') {
                if (!st.isEmpty()) st.pop();
            } else {
                st.push(s.charAt(i));
            }
        }

        s = "";
        for (char x : st) s += x;

        st.clear();

        for (int i = 0; i < t.length(); i++) {
            if (t.charAt(i) == '#') {
                if (!st.isEmpty()) st.pop();
            } else {
                st.push(t.charAt(i));
            }
        }

        t = "";
        for (char x : st) t += x;

        return s.equals(t);
    }
}
```
<img width="1919" height="1032" alt="image" src="https://github.com/user-attachments/assets/0777fc5b-a8e5-4a90-a9fd-aa0d327bb7be" />
