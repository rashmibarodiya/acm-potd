# Remove Duplicates from Sorted Linked List (Java)

## Description
Removes duplicate nodes from a sorted singly linked list so that each element appears only once.

## Approach
- Use two pointers: `prev` and `ptr`
- Traverse the list
- If values are equal, skip the duplicate node
- Otherwise, move both pointers forward

## Complexity
- Time: O(n)
- Space: O(1)

## Code
```java
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        if(head == null || head.next == null) return head;

        ListNode ptr = head.next, prev = head;

        while(ptr != null){
            if(prev.val == ptr.val){
                ptr = ptr.next;
                prev.next = ptr;
            } else {
                prev = ptr;
                ptr = ptr.next;
            }
        }
        return head;
    }
}
```
<img width="1919" height="1031" alt="image" src="https://github.com/user-attachments/assets/7d1f8c3a-87fb-45c6-8372-ad8d9c4addad" />
