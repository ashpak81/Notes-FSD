# Queue Data Structure

## What is a Queue?

A **queue** is a linear data structure that follows the **FIFO (First In First Out)** principle. Elements are added at the end and removed from the front.

## Why Use a Queue?

- **Order Processing**: Manages tasks in the order they are received.
- **Buffering**: Handles data transfer between processes.
- **Task Scheduling**: Manages tasks in the order they are scheduled.
- **Breadth-First Search (BFS)**: Used in graph traversal.

## Advantages

- **Order Preservation**: Maintains the sequence of elements.
- **Simple Operations**: Easy to understand and implement.
- **Predictable Access**: Ensures consistent processing order.

## Disadvantages

- **Limited Access**: Only the front and rear elements are directly accessible.
- **Fixed Size**: Can have overflow issues if array-based.

## Time Complexity

- **Insertion (Enqueue)**: O(1)
- **Deletion (Dequeue)**: O(1)
- **Access (Peek)**: O(1)

## Real-Life Example

- **Queue at a Ticket Counter**: The first person in line is served first.

## Use Cases

- **Order Processing**: Systems that process tasks in the order they arrive.
- **Print Queue**: Manages print jobs sequentially.
- **Data Buffering**: Handles streaming data.
- **Task Scheduling**: In operating systems for managing tasks.

## In-Built Methods

- **`offer(E e)`**: Adds an item to the end. Returns `true` if successful, `false` if the queue is full. **Time Complexity: O(1)**
- **`poll()`**: Removes and returns the front item. Returns `null` if the queue is empty. **Time Complexity: O(1)**
- **`remove()`**: Removes and returns the front item. Throws `NoSuchElementException` if empty. **Time Complexity: O(1)**
- **`peek()`**: Returns the front item without removing it. Throws `NoSuchElementException` if empty. **Time Complexity: O(1)**
- **`pollLast()`**: Removes and returns the last item. Returns `null` if empty. **Time Complexity: O(1)**
- **`peekLast()`**: Returns the last item without removing it. Returns `null` if empty. **Time Complexity: O(1)**
- **`clear()`**: Removes all items from the queue. **Time Complexity: O(n)**
- **`contains(Object o)`**: Checks if an item is present. Returns `true` if present, otherwise `false`. **Time Complexity: O(n)**
- **`isEmpty()`**: Checks if the queue is empty. **Time Complexity: O(1)**
- **`size()`**: Returns the number of items. **Time Complexity: O(1)**

## Example Code

Here’s a simple Java implementation of a queue:

```java
import java.util.Deque;
import java.util.LinkedList;
import java.util.NoSuchElementException;

public class Queue<T> {
    private Deque<T> deque = new LinkedList<>();

    public boolean offer(T item) {
        return deque.offerLast(item);
    }

    public T dequeue() {
        if (isEmpty()) {
            throw new NoSuchElementException("Queue is empty");
        }
        return deque.removeFirst();
    }

    public T poll() {
        return deque.pollFirst();
    }

    public T peek() {
        if (isEmpty()) {
            throw new NoSuchElementException("Queue is empty");
        }
        return deque.getFirst();
    }

    public T pollLast() {
        return deque.pollLast();
    }

    public T peekLast() {
        return deque.peekLast();
    }

    public void clear() {
        deque.clear();
    }

    public boolean contains(T item) {
        return deque.contains(item);
    }

    public boolean isEmpty() {
        return deque.isEmpty();
    }

    public int size() {
        return deque.size();
    }

    public static void main(String[] args) {
        Queue<Integer> queue = new Queue<>();
        queue.offer(1);
        queue.offer(2);
        queue.offer(3);

        System.out.println("Front element (peek): " + queue.peek());  // Output: 1
        System.out.println("Queue size: " + queue.size());           // Output: 3

        System.out.println("Dequeued element: " + queue.dequeue());  // Output: 1
        System.out.println("Queue size after dequeue: " + queue.size()); // Output: 2

        System.out.println("Polled element: " + queue.poll());        // Output: 2
        System.out.println("Polled element from empty queue: " + queue.poll()); // Output: null

        System.out.println("Peek last element: " + queue.peekLast()); // Output: 3
        System.out.println("Polled last element: " + queue.pollLast()); // Output: 3

        System.out.println("Contains 2? " + queue.contains(2)); // Output: false

        queue.clear();
        System.out.println("Queue size after clear: " + queue.size()); // Output: 0
    }
}
```
