# Intersection of Two Linked Lists (Java)

## Description
Finds the node where two singly linked lists intersect. Returns the intersection node or null if no intersection exists.

## Approach
- Count lengths of both lists
- Align starting points by skipping extra nodes in the longer list
- Traverse both lists together to find intersection

## Complexity
- Time: O(n + m)
- Space: O(1)

## Code
```java
public class Solution {
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        if (headA == headB) return headA;

        int a = 0, b = 0;
        ListNode ha = headA, hb = headB;

        while (ha != null) {
            ha = ha.next;
            a++;
        }
        while (hb != null) {
            hb = hb.next;
            b++;
        }

        ha = headA;
        hb = headB;

        int diff = a - b;

        if (diff > 0) {
            while (diff-- > 0) ha = ha.next;
        } else {
            while (diff++ < 0) hb = hb.next;
        }

        while (ha != hb && ha != null) {
            ha = ha.next;
            hb = hb.next;
        }

        return ha;
    }
}
```
<img width="1919" height="1036" alt="image" src="https://github.com/user-attachments/assets/ec91cff7-feb2-4213-a6a4-269c41e591fb" />
