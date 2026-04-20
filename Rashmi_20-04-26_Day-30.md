# Power of Two (Java)

## Description
Checks whether a given integer `n` is a power of two.

## Approach
- A power of two has only one set bit in binary
- Use bit manipulation:
  - `n & (n - 1)` removes the lowest set bit
  - If result is `0`, then `n` had only one set bit

## Complexity
- Time: O(1)  
- Space: O(1)

## Code
```java
class Solution {
    public boolean isPowerOfTwo(int n) {
        return n > 0 && (n & (n - 1)) == 0;
    }
}
```
<img width="1910" height="1034" alt="image" src="https://github.com/user-attachments/assets/aeb2ee81-caed-48e4-8b09-4a4b05f1c509" />
