#  Two Sum Problem (Java Solution)

##  Problem Statement
Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to the target.

- Each input has exactly one solution.
- You cannot use the same element twice.

---

##  Approach
This solution uses a **HashMap** for efficient lookup.

### Steps:
1. Store each element in a HashMap:
   - Key → value of element
   - Value → index
2. Traverse the array again:
   - Compute `needed = target - nums[i]`
   - Check if `needed` exists in the map
   - Ensure it's not the same index
3. Return the indices

---

##  Complexity
- **Time Complexity:** O(n)  
- **Space Complexity:** O(n)

---

##  Code

<img width="1919" height="859" alt="image" src="https://github.com/user-attachments/assets/fb89fba5-9664-4c54-9ddc-363a16e6ca08" />
