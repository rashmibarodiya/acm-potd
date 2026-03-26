# Move Zeroes (Java Solution)

##  Problem Statement
Given an integer array `nums`, move all `0`s to the end while maintaining the relative order of non-zero elements.

- The operation must be done **in-place**
- Minimize the number of operations

---

##  Approach
This solution uses a **two-pointer technique**.

### Steps:
1. Initialize:
   - `idx = 0` → position to place non-zero elements
   - `cnt = 0` → count of zeroes
2. Traverse the array:
   - If element is `0`, increment `cnt`
   - Else, place it at `nums[idx]` and increment `idx`
3. Fill remaining positions from the end with `0`s using `cnt`

---

## Complexity
- **Time Complexity:** O(n)  
- **Space Complexity:** O(1)

---

<img width="1919" height="1031" alt="Screenshot 2026-03-26 224135" src="https://github.com/user-attachments/assets/2e68bd78-8f54-423b-a1c0-ed2ec381f73f" />

