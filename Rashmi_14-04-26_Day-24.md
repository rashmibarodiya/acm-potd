# Find Center of Star Graph (Java)

## Description
Finds the center node of a star graph. In a star graph, one central node is connected to all other nodes.

## Approach
- A star graph center appears in every edge
- Compare first two edges:
  - The common node between them is the center

## Complexity
- Time: O(1)  
- Space: O(1)

## Code
```java
class Solution {
    public int findCenter(int[][] edges) {
        if (edges[0][0] == edges[1][0] || edges[0][0] == edges[1][1]) {
            return edges[0][0];
        } else {
            return edges[0][1];
        }
    }
}
```
<img width="1919" height="1026" alt="image" src="https://github.com/user-attachments/assets/0c142488-ba21-4b32-a00b-075e4e9e2d11" />
