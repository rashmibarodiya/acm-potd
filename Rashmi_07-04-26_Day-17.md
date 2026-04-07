# Implement Stack using Queue (Java)

## Description
Implements a stack using a single queue. Supports push, pop, top, and empty operations.

## Approach
- Use one queue
- On push:
  - Add element to queue
  - Rotate previous elements to maintain LIFO order
- Front of queue always represents top of stack

## Complexity
- Push: O(n)  
- Pop: O(1)  
- Top: O(1)  
- Space: O(n)

## Code
```java
import java.util.*;

class MyStack {
    Queue<Integer> q;

    public MyStack() {
        q = new LinkedList<>();
    }
    
    public void push(int x) {
        q.add(x);
        for(int i = 0; i < q.size() - 1; i++){
            q.add(q.poll());
        }
    }
    
    public int pop() {
        return q.poll();
    }
    
    public int top() {
        return q.peek();
    }
    
    public boolean empty() {
        return q.size() == 0;
    }
}
```
<img width="1919" height="1029" alt="image" src="https://github.com/user-attachments/assets/ac09801e-ad41-4ecf-923b-36e0fee0b302" />
