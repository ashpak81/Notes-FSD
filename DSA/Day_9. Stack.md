# Understanding Stack Data Structure

## What is a Stack?

A **stack** is a linear data structure where both insertion and deletion operations are performed from one end, known as the **top**. It adheres to the **LIFO (Last In First Out)** principle, meaning the last item added is the first one to be removed.

## Why Use a Stack?

1. **Undo Operation**: Allows reverting to a previous state in applications.
2. **Redo Operation**: Enables reapplication of a previously undone action.
3. **Ticket Booking**: Manages reservations using a Last In, First Out order.
4. **Syntax Checking**: Validates expressions in programming languages to ensure correct syntax.

## Advantages and Disadvantages

### Advantages

- **Simple Implementation**: Can be easily implemented using arrays or linked lists.
- **Fast Access**: Operations like push and pop have constant time complexity (O(1)).
- **Memory Efficiency**: Allocates memory dynamically as needed.

### Disadvantages

- **Limited Access**: Direct access is restricted to the top element only.
- **Overflow and Underflow**: Issues may arise with fixed-size implementations or improper operation management.

## Time Complexity

- **Insertion (Push)**: O(1) - Adding an item to the top of the stack takes constant time.
- **Deletion (Pop)**: O(1) - Removing the top item of the stack also takes constant time.
- **Access (Peek)**: O(1) - Accessing the top item without removing it is performed in constant time.
- **Accessing Middle Element**: O(n) - Accessing an element not at the top requires traversing the entire stack, which takes linear time.

## Real-Life Example

- **Stack of Plates**: Similar to a stack of plates where plates are added or removed from the top.

## Use Cases

1. **Backtracking**: Used in algorithms like Depth-First Search (DFS).
2. **Expression Evaluation**: Converting infix expressions to postfix notation.

## Program Example

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

    // Pushes an item onto the stack
    public void push(T item) {
        top = new Node<>(item, top);
        size++;
    }

    // Removes and returns the item at the top of the stack
    public T pop() {
        if (isEmpty()) {
            throw new EmptyStackException();
        }
        T item = top.data;
        top = top.next;
        size--;
        return item;
    }

    // Returns the item at the top of the stack without removing it
    public T peek() {
        if (isEmpty()) {
            throw new EmptyStackException();
        }
        return top.data;
    }

    // Returns true if the stack is empty
    public boolean isEmpty() {
        return top == null;
    }

    // Returns the number of items in the stack
    public int size() {
        return size;
    }

    // Accesses the middle element (not efficient, included for completeness)
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

        System.out.println("Top element: " + stack.peek());  // Output: Top element: 3
        System.out.println("Stack size: " + stack.size());   // Output: Stack size: 3

        System.out.println("Popped element: " + stack.pop());  // Output: Popped element: 3
        System.out.println("Stack size after pop: " + stack.size());  // Output: Stack size after pop: 2

        System.out.println("Middle element: " + stack.getMiddleElement());  // Output: Middle element: 1
    }
}
```

### Explanation:

- **`Node<T>`**: A private inner class representing each element in the stack.
- **`push(T item)`**: Adds an item to the top of the stack. **Time Complexity: O(1)**
- **`pop()`**: Removes and returns the top item of the stack. **Time Complexity: O(1)**
- **`peek()`**: Returns the top item without removing it. **Time Complexity: O(1)**
- **`getMiddleElement()`**: Accesses the middle element of the stack. **Time Complexity: O(n)**
- **`isEmpty()`**: Checks if the stack is empty.
- **`size()`**: Returns the number of items in the stack.
