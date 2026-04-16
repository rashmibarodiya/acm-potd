# Invert Binary Tree (Java)

## Description
Inverts a binary tree by swapping left and right children of every node.

## Approach
- Use BFS (queue)
- Traverse each node
- Swap its left and right children
- Add children to queue for further processing

## Complexity
- Time: O(n)  
- Space: O(n)

## Code
```java
import java.util.*;

class Solution {
    public TreeNode invertTree(TreeNode root) {
        if (root == null) return null;

        Queue<TreeNode> q = new LinkedList<>();
        q.add(root);

        while (!q.isEmpty()) {
            TreeNode c = q.poll();

            TreeNode t = c.left;
            c.left = c.right;
            c.right = t;

            if (c.left != null) q.add(c.left);
            if (c.right != null) q.add(c.right);
        }

        return root;
    }
}
```
<img width="1919" height="1027" alt="image" src="https://github.com/user-attachments/assets/0ff41b26-9ba8-4280-84f3-a2b324b42f7b" />
