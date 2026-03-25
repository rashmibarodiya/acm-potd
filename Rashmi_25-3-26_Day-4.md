# Missing Number (Java Solution)

##  Problem Statement
Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.

---

##  Approach
This solution uses an **extra array (marking technique)**.

### Steps:
1. Create an auxiliary array `arr` of size `n + 1` and initialize all values to `-1`.
2. Traverse the given array and mark the visited indices:
   - For each number `x` in `nums`, set `arr[x] = 1`
3. Traverse the auxiliary array:
   - The index with value `-1` is the missing number

---

##  Complexity
- **Time Complexity:** O(n)  
- **Space Complexity:** O(n)
<img width="1919" height="1021" alt="image" src="https://github.com/user-attachments/assets/dfc5dc54-cd8d-4bae-ab97-77f37c59d4c8" />


---
