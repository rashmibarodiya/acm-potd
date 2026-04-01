## Merge Two Sorted Linked Lists

This program merges two sorted singly linked lists into one sorted list.

### Approach:
- If one list is empty, return the other.
- Choose the smaller starting node as the head.
- Traverse both lists and keep attaching the smaller node.
- When one list ends, attach the remaining nodes of the other list.

### Time Complexity:
- O(n + m)

---

## Java Code

```java
class ListNode {
    int val;
    ListNode next;

    ListNode() {}
    ListNode(int val) { this.val = val; }
    ListNode(int val, ListNode next) {
        this.val = val;
        this.next = next;
    }
}

class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {

        if (list1 == null) return list2;
        if (list2 == null) return list1;

        ListNode head;

        if (list1.val <= list2.val) {
            head = list1;
            list1 = list1.next;
        } else {
            head = list2;
            list2 = list2.next;
        }

        ListNode current = head;

        while (list1 != null && list2 != null) {
            if (list1.val <= list2.val) {
                current.next = list1;
                list1 = list1.next;
            } else {
                current.next = list2;
                list2 = list2.next;
            }
            current = current.next;
        }

        if (list1 != null) current.next = list1;
        if (list2 != null) current.next = list2;

        return head;
    }
}

```
<img width="1919" height="1002" alt="image" src="https://github.com/user-attachments/assets/58ae37d9-9641-47a5-b6ad-cd2f363f9445" />
