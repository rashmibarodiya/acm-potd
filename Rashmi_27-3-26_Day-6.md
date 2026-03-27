#  Check If N and Its Double Exist (Sorting + Binary Search)

##  Problem Statement
Given an integer array `arr`, return `true` if there exist two indices `i` and `j` such that:

- `i != j`
- `arr[i] == 2 * arr[j]`

Otherwise, return `false`.

---

## Approach (Sorting + Binary Search)
This solution uses:
- **Sorting** to enable binary search
- **Binary Search** to find `2 * arr[i]`

### Steps:
1. Sort the array.
2. For each element `arr[i]`:
   - Compute `x = 2 * arr[i]`
   - Use binary search to find `x` in the array
   - Ensure the index is different (`i != mid`)
3. If found → return `true`

---


##  Complexity
- **Time Complexity:** `O(n log n)` (sorting + binary search)  
- **Space Complexity:** `O(1)` (in-place sorting)

---

##  Code
```java
<img width="1919" height="1030" alt="image" src="https://github.com/user-attachments/assets/2f372133-ec9a-4d35-80f2-cd98abf79547" />
