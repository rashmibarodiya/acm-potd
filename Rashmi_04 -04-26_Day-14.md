# Palindrome Linked List (Java)

## Description
Checks whether a singly linked list is a palindrome.

## Approach
- Use slow and fast pointers to find the middle
- Reverse the second half of the list
- Compare first half and second half
- Restore the list (optional)

## Complexity
- Time: O(n)
- Space: O(1)

## Code
```java
class Solution {
    public ListNode reverseList(ListNode head) {
        if(head == null) return null;

        ListNode p = null, c = head, n = head.next;

        while(c != null){
            c.next = p;
            p = c;
            c = n;
            if(n != null) n = n.next;
        }
        return p;
    }

    public boolean isPalindrome(ListNode head) {
        ListNode slow = head, fast = head;

        while(fast.next != null && fast.next.next != null){
            slow = slow.next;
            fast = fast.next.next;
        }

        slow.next = reverseList(slow.next);

        ListNode start = head, midN = slow.next;

        while(midN != null){
            if(midN.val != start.val) return false;
            start = start.next;
            midN = midN.next;
        }

        slow.next = reverseList(slow.next);

        return true;
    }
}
```
<img width="1913" height="1033" alt="image" src="https://github.com/user-attachments/assets/30cef683-903e-4db2-ab53-77d405e36501" />
