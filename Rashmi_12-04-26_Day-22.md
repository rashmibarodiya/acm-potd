# Flood Fill (DFS - Java)

## Description
Changes the color of a region in a 2D image starting from a given pixel. All connected pixels with the same original color are updated.

## Approach
- Use DFS to traverse in 4 directions
- Stop if:
  - Out of bounds
  - Pixel color is not the original color
- Update current pixel and continue DFS

## Complexity
- Time: O(m × n)  
- Space: O(m × n) (recursion stack)

## Code
```java
class Solution {
    public void dfs(int[][] image, int sr, int sc, int org, int color) {
        int m = image.length, n = image[0].length;

        if (sr < 0 || sc < 0 || sr >= m || sc >= n || image[sr][sc] != org)
            return;

        image[sr][sc] = color;

        dfs(image, sr - 1, sc, org, color);
        dfs(image, sr + 1, sc, org, color);
        dfs(image, sr, sc - 1, org, color);
        dfs(image, sr, sc + 1, org, color);
    }

    public int[][] floodFill(int[][] image, int sr, int sc, int color) {
        if (image[sr][sc] == color)
            return image;

        dfs(image, sr, sc, image[sr][sc], color);
        return image;
    }
}
```
<img width="1919" height="1033" alt="image" src="https://github.com/user-attachments/assets/5b0d5322-ccb3-48c2-bc61-a96d102462d3" />
