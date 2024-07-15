
# Linked List Notes in Java

## Basics

1. A linked list is a linear data structure that stores elements in non-contiguous memory locations.
2. Each element in a linked list is called a node.
3. Each node contains two parts:
  - **Data**: The actual value stored in the node.
  - **Next**: A reference (or pointer) to the next node in the list.4.
4. The first node is called the **head**. It is a special node but not a keyword.
5. The last node is called the **tail** and its address is `null`, indicating the end of the list.
6. Insertion and deletion in a linked list happen in constant time \(O(1)\), while random access happens in \(O(n)\) time.





## Types of Linked Lists

### Singly Linked List
- Each node points to the next node in the list.
- You can only traverse the list in one direction (from head to tail).

### Doubly Linked List
- Each node has two references: one pointing to the next node and another pointing to the previous node.
- You can traverse the list in both directions.

### Circular Linked List
- The last node points back to the first node, creating a circular structure.

## Java Implementation

- Java provides a built-in `LinkedList` class that implements the `List` and `Deque` interfaces.
- It uses a doubly linked list internally, allowing for efficient insertion and deletion operations at both ends.

## Common Operations

- `add(E e)`: Adds an element to the end of the list.
- `add(int index, E e)`: Inserts an element at the specified index.
- `remove(Object o)`: Removes the first occurrence of the specified element.
- `remove(int index)`: Removes the element at the specified index.
- `get(int index)`: Returns the element at the specified index.
- `set(int index, E e)`: Replaces the element at the specified index with the specified element.
- `size()`: Returns the number of elements in the list.
- `isEmpty()`: Returns true if the list is empty, false otherwise.

## Advantages of Linked Lists

- **Dynamic size**: Can grow or shrink dynamically as elements are added or removed.
- **Efficient insertion and deletion**: Inserting or deleting an element at the beginning or middle of the list is faster than in an array.
- **No memory waste**: Memory is allocated dynamically as needed.

## Disadvantages of Linked Lists

- **Slower access time**: Accessing an element at a specific index requires traversing the list from the beginning until the desired index is reached.
- **Increased memory usage**: Each node requires additional memory to store the next reference (and previous reference in a doubly linked list).

## Example

```java
import java.util.LinkedList;

public class LinkedListExample {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();
        list.add("Apple");
        list.add("Banana");
        list.add(1, "Orange"); 

        System.out.println(list.get(0)); // Output: Apple

        list.remove("Banana"); 

        for (String fruit : list) {
            System.out.println(fruit); 
        }
    }
}
```


### Custom Linked List Implementation

If you want to implement your own linked list from scratch, here's a basic example:

```java
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class CustomLinkedList {
    Node head;

    public void add(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
        } else {
            Node current = head;
            while (current.next != null) {
                current = current.next;
            }
            current.next = newNode;
        }
    }

    public void printList() {
        Node current = head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
    }

    public static void main(String[] args) {
        CustomLinkedList list = new CustomLinkedList();
        list.add(1);
        list.add(2);
        list.add(3);

        list.printList(); // Output: 1 2 3
    }
}
```
