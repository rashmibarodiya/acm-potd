# Maximum Depth of Binary Tree (C++)

## Description
Finds the maximum depth (height) of a binary tree. Depth is the number of nodes along the longest path from root to a leaf.

## Approach
- Use recursion (DFS)
- For each node:
  - Compute depth of left subtree
  - Compute depth of right subtree
  - Return max of both + 1

## Complexity
- Time: O(n)  
- Space: O(h) (recursion stack, h = height)

## Code
```cpp
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if(!root) return 0;

        int l = maxDepth(root->left);
        int r = maxDepth(root->right);

        return max(l, r) + 1;
    }   
};
```
<img width="1919" height="1023" alt="image" src="https://github.com/user-attachments/assets/a8e31137-43cf-4534-96de-79c068b4609f" />
