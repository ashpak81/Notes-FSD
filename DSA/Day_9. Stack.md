# Stack Data Structure

### What is a Stack?

A **stack** is a linear data structure where insertion and deletion are done at one end called the **top**. It follows the **LIFO (Last In First Out)** principle, meaning the most recently added item is the first one to be removed.

### Why Use a Stack?

- **Undo Operation**: Revert to previous states in applications.
- **Redo Operation**: Reapply actions that were undone.
- **Ticket Booking**: Manage reservations with a Last In, First Out order.
- **Syntax Checking**: Validate expressions in programming languages.

### Advantages

- **Simple Implementation**: Easy to implement with arrays or linked lists.
- **Fast Operations**: Push and pop operations are O(1).
- **Memory Efficiency**: Uses memory dynamically as needed.

### Disadvantages

- **Limited Access**: Only the top element can be accessed directly.
- **Overflow/Underflow**: Issues with fixed-size stacks or mismanaged operations.

### Time Complexity

- **Push**: O(1) - Adding an item to the top.
- **Pop**: O(1) - Removing the top item.
- **Peek**: O(1) - Accessing the top item.
- **Accessing Middle Element**: O(n) - Requires traversing the stack.

### Real-Life Example

- **Stack of Plates**: Plates are added or removed from the top of the stack.

### Use Cases

- **Backtracking**: Algorithms like Depth-First Search (DFS).
- **Expression Evaluation**: Converting infix expressions to postfix notation.

### In-Built Methods

1. **`push(T item)`**

- **Description**: Adds an item to the top of the stack.
- **Time Complexity**: O(1)

2. **`pop()`**

- **Description**: Removes and returns the top item. Throws `EmptyStackException` if the stack is empty.
- **Time Complexity**: O(1)

3. **`peek()`**

- **Description**: Returns the top item without removing it. Throws `EmptyStackException` if the stack is empty.
- **Time Complexity**: O(1)

4. **`isEmpty()`**

- **Description**: Checks if the stack is empty.
- **Time Complexity**: O(1)

5. **`size()`**

- **Description**: Returns the number of items in the stack.
- **Time Complexity**: O(1)

6. **`getMiddleElement()`**

- **Description**: Returns the middle element of the stack (inefficient for large stacks).
- **Time Complexity**: O(n)

### Example Code

```java
import java.util.EmptyStackException;

public class Stack<T> {
    private Node<T> top;
    private int size;

    private static class Node<T> {
        private T data;
        private Node<T> next;

        private Node(T data, Node<T> next) {
            this.data = data;
            this.next = next;
        }
    }

    public Stack() {
        top = null;
        size = 0;
    }

    public void push(T item) {
        top = new Node<>(item, top);
        size++;
    }

    public T pop() {
        if (isEmpty()) {
            throw new EmptyStackException();
        }
        T item = top.data;
        top = top.next;
        size--;
        return item;
    }

    public T peek() {
        if (isEmpty()) {
            throw new EmptyStackException();
        }
        return top.data;
    }

    public boolean isEmpty() {
        return top == null;
    }

    public int size() {
        return size;
    }

    public T getMiddleElement() {
        if (isEmpty()) {
            throw new EmptyStackException();
        }
        Node<T> current = top;
        int middleIndex = size / 2;
        for (int i = 0; i < middleIndex; i++) {
            current = current.next;
        }
        return current.data;
    }

    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);

        System.out.println("Top element: " + stack.peek());  // Output: 3
        System.out.println("Stack size: " + stack.size());   // Output: 3

        System.out.println("Popped element: " + stack.pop());  // Output: 3
        System.out.println("Stack size after pop: " + stack.size());  // Output: 2

        System.out.println("Middle element: " + stack.getMiddleElement());  // Output: 1
    }
}
```

#### Explanation

- **`Node<T>`**: Represents each element in the stack.
- **`push(T item)`**: Adds an item to the top. **O(1)**
- **`pop()`**: Removes and returns the top item. **O(1)**
- **`peek()`**: Returns the top item. **O(1)**
- **`getMiddleElement()`**: Returns the middle element. **O(n)**
- **`isEmpty()`**: Checks if the stack is empty. **O(1)**
- **`size()`**: Returns the number of items. **O(1)**
