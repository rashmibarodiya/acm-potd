# Remove All Adjacent Duplicates in String (Java)

## Description
Removes all adjacent duplicate characters in a string repeatedly until no duplicates remain.

## Approach
- Use `StringBuilder` as a stack
- Traverse characters:
  - If current char matches last character → remove last
  - Else → append character
- Track current size using `n`

## Complexity
- Time: O(n)  
- Space: O(n)

## Code
```java
class Solution {
    public String removeDuplicates(String s) {
        StringBuilder sb = new StringBuilder();
        int n = 0;

        for (char c : s.toCharArray()) {
            if(n != 0 && c == sb.charAt(n - 1)) {
                sb.deleteCharAt(n-- - 1);
            } else {
                sb.append(c);
                n++;
            }
        }
        
        return sb.toString();
    }
}
```
<img width="1919" height="1030" alt="image" src="https://github.com/user-attachments/assets/216af7ce-1522-4540-a03b-3db168b5158e" />
