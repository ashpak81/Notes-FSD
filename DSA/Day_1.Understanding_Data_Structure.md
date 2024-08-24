

## Data Structures

**Data structures** are crucial in computer science for organizing and managing data efficiently. They allow for fast data retrieval, modification, and storage, thus enhancing the performance of applications and systems.

### 1. Array

**Definition:** An array is a collection of elements of the same type stored in contiguous memory locations. Each element can be accessed by an index.

**Characteristics:**
- **Fixed Size:** The size of the array is defined at the time of creation and cannot be changed.
- **Indexing:** Elements are accessed using indices, starting from zero.

**Real-world Examples:**
- **Database:** Storing rows of data.
- **Game Development:** Managing levels, inventory items, or character attributes.
- **Scheduling:** Representing lists of tasks or events.

**Example:**
```java
int[] numbers = {1, 2, 3, 4, 5}; // Array of integers
System.out.println(numbers[2]);  // Outputs: 3
```

### 2. Stack

**Definition:** A stack is a linear data structure that operates on a Last In First Out (LIFO) basis. Elements are added and removed from the same end, called the top of the stack.

**Characteristics:**
- **Push:** Add an element to the top of the stack.
- **Pop:** Remove the top element from the stack.
- **Peek:** Access the top element without removing it.

**Real-world Examples:**
- **Undo Operations:** Reverting changes in text editors.
- **Function Call Management:** Managing function calls and local variables in programming languages.

**Example:**
```java
import java.util.Stack;

Stack<Integer> stack = new Stack<>();
stack.push(1);
stack.push(2);
stack.push(3);
System.out.println(stack.pop()); // Outputs: 3
```

### 3. Queue

**Definition:** A queue is a linear data structure that follows the First In First Out (FIFO) principle. Elements are added at the rear and removed from the front.

**Characteristics:**
- **Enqueue:** Add an element to the rear of the queue.
- **Dequeue:** Remove the front element of the queue.
- **Front:** Access the front element without removing it.

**Real-world Examples:**
- **Ticketing Systems:** Managing customers in a service queue.
- **Print Spooling:** Managing print jobs in a printer.

**Example:**
```java
import java.util.LinkedList;
import java.util.Queue;

Queue<Integer> queue = new LinkedList<>();
queue.add(1);
queue.add(2);
queue.add(3);
System.out.println(queue.poll()); // Outputs: 1
```

### 4. Linked List

**Definition:** A linked list is a linear data structure where elements, called nodes, are connected by pointers. Each node contains data and a reference to the next node.

**Characteristics:**
- **Dynamic Size:** Can grow or shrink in size by adding or removing nodes.
- **Nodes:** Each node contains data and a reference to the next node (and sometimes to the previous node).

**Real-world Examples:**
- **Music Playlists:** Managing songs in sequence.
- **Train or Subway Cars:** Representing a sequence of connected train cars.

**Example:**
```java
class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class LinkedList {
    Node head;
    void append(int data) {
        if (head == null) {
            head = new Node(data);
            return;
        }
        Node current = head;
        while (current.next != null) {
            current = current.next;
        }
        current.next = new Node(data);
    }
}
```

### 5. Trees

**Definition:** A tree is a non-linear data structure with a hierarchical structure consisting of nodes, with a single root node and zero or more child nodes.

**Characteristics:**
- **Root:** The topmost node in the tree.
- **Leaf Nodes:** Nodes with no children.
- **Internal Nodes:** Nodes with at least one child.

**Real-world Examples:**
- **File Systems:** Hierarchical organization of files and directories.
- **Organizational Charts:** Representing company structures.

**Example:**
```java
class TreeNode {
    int value;
    TreeNode left, right;
    TreeNode(int item) {
        value = item;
        left = right = null;
    }
}

public class BinaryTree {
    TreeNode root;
}
```

### 6. Hashtable, HashSet, and HashMap

**Definitions:**
- **Hashtable:** A collection that maps keys to values using a hash function. It does not allow duplicate keys.
- **HashMap:** Similar to Hashtable but allows null values and is not synchronized.
- **HashSet:** A collection of unique elements, implemented using a hash table.

**Characteristics:**
- **Hashing:** Uses a hash function to compute an index into an array of buckets.
- **Efficiency:** Provides fast insertion, deletion, and lookup operations.

**Real-world Examples:**
- **Database Indexing:** Efficiently managing and retrieving records.
- **DNS Resolution:** Mapping domain names to IP addresses.

**Example:**
```java
import java.util.HashMap;

HashMap<String, Integer> map = new HashMap<>();
map.put("Apple", 1);
map.put("Banana", 2);
System.out.println(map.get("Apple")); // Outputs: 1
```

### 7. Graph

**Definition:** A graph is a collection of nodes (vertices) connected by edges. It can be used to represent various relationships between entities.

**Characteristics:**
- **Vertices:** Nodes in the graph.
- **Edges:** Connections between vertices.
- **Directed and Undirected:** Edges can have direction or be bidirectional.

**Real-world Examples:**
- **Social Networks:** Representing friendships and connections.
- **Navigation Systems:** Mapping routes and distances.

**Example:**
```java
import java.util.*;

class Graph {
    private Map<Integer, List<Integer>> adjList = new HashMap<>();

    void addVertex(int v) {
        adjList.putIfAbsent(v, new ArrayList<>());
    }

    void addEdge(int v1, int v2) {
        adjList.get(v1).add(v2);
        adjList.get(v2).add(v1); // For undirected graph
    }
}
```
