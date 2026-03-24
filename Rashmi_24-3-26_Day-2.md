
Best Time to Buy and Sell Stock – Approach

We iterate through the array while tracking the minimum price index seen so far. At each step, we calculate the profit by selling on the current day and buying at the minimum price encountered earlier. We update the maximum profit accordingly. If a new lower price is found, we update the buying index.
Key Idea
Buy at the lowest price so far
Sell at the current price
Track maximum profit


Complexity
Time: O(n)
Space: O(1)

<img width="1914" height="1030" alt="image" src="https://github.com/user-attachments/assets/99921718-7d5a-42fa-9356-d2d39ec6467e" />
