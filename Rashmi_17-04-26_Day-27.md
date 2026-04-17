# Diameter of Binary Tree (Java)

## Description
Finds the diameter of a binary tree. Diameter is the length of the longest path between any two nodes (number of edges).

## Approach
- Use DFS recursion
- For each node:
  - Compute height of left and right subtree
  - Update diameter as `left + right`
- Return height to parent

## Complexity
- Time: O(n)  
- Space: O(h)

## Code
```java
class Solution {
    public int diameterOfBinaryTree(TreeNode root) {
        if (root == null) return 0;

        int[] result = {Integer.MIN_VALUE};
        helper(root, result);

        return result[0];
    }
    
    public int helper(TreeNode root, int[] result) {
        if (root == null) return 0;

        int left = helper(root.left, result);
        int right = helper(root.right, result);

        result[0] = Math.max(result[0], left + right);

        return Math.max(left, right) + 1;
    }
}
```
<img width="1919" height="1033" alt="image" src="https://github.com/user-attachments/assets/bb788da4-14df-4bfe-96e3-690b05df501d" />
