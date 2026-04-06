# Implement Queue using Stacks (Java)

## Description
Implements a queue using two stacks. Supports standard queue operations: push, pop, peek, and empty.

## Approach
- Use two stacks:
  - `st1` for incoming elements
  - `st2` for outgoing elements
- For pop/peek:
  - If `st2` is empty, transfer all elements from `st1` to `st2`
  - This reverses order to maintain FIFO

## Complexity
- Push: O(1)  
- Pop: Amortized O(1)  
- Peek: Amortized O(1)  
- Space: O(n)

## Code
```java
import java.util.*;

class MyQueue {
    Stack<Integer> st1, st2;

    public MyQueue() {
        st1 = new Stack<>();
        st2 = new Stack<>();
    }
    
    public void push(int x) {
        st1.push(x);
    }
    
    public int pop() {
        if(st2.isEmpty()){
            while(!st1.isEmpty()){
                st2.push(st1.pop());
            }
        }
        return st2.pop();
    }
    
    public int peek() {
        if(st2.isEmpty()){
            while(!st1.isEmpty()){
                st2.push(st1.pop());
            }
        }
        return st2.peek();
    }
    
    public boolean empty() {
        return st1.isEmpty() && st2.isEmpty();
    }
}
```
<img width="1919" height="1025" alt="image" src="https://github.com/user-attachments/assets/654cabb4-9d04-4069-b1e4-9b5339d9cff7" />
