# Remove Outermost Parentheses (Java)

## Description
Removes the outermost parentheses from every primitive valid parentheses substring.

## Approach
- Track number of opened brackets using `opened`
- For `(`:
  - Add only if already inside a group (`opened > 0`)
- For `)`:
  - Add only if more than one open bracket exists (`opened > 1`)
- Increment/decrement `opened` accordingly

## Complexity
- Time: O(n)  
- Space: O(n)

## Code
```java
class Solution {
    public String removeOuterParentheses(String S) {
        StringBuilder s = new StringBuilder();
        int opened = 0;

        for (char c : S.toCharArray()) {
            if (c == '(' && opened++ > 0) s.append(c);
            if (c == ')' && opened-- > 1) s.append(c);
        }

        return s.toString();
    }
}
```
<img width="1919" height="1032" alt="image" src="https://github.com/user-attachments/assets/b225df08-7294-4915-b0b8-9cad36db6764" />
