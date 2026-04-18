# Subtree of Another Tree (Java)

## Description
Checks whether a binary tree `subRoot` is a subtree of another tree `root`.

## Approach
- Traverse each node of `root`
- At each node, check if trees are identical using helper `same`
- If match found → return true
- Otherwise, check left and right subtrees

## Complexity
- Time: O(n * m)  
- Space: O(h)

## Code
```java
class Solution {
    public boolean isSubtree(TreeNode root, TreeNode subRoot) {
        if (root == null) return false;

        if (same(root, subRoot)) return true;

        return isSubtree(root.left, subRoot) || isSubtree(root.right, subRoot);
    }

    public boolean same(TreeNode root, TreeNode sub) {
        if (root == null && sub == null) return true;
        if (root == null || sub == null) return false;

        if (root.val != sub.val) return false;

        return same(root.left, sub.left) && same(root.right, sub.right);
    }
}
```
<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/ada57f83-fe80-4ce0-9e30-ff9d4dc19c67" />
