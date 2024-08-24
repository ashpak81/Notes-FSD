
## Algorithms

### 1. Sorting Algorithms

**Definition:** Sorting algorithms rearrange elements in a collection, such as an array or list, into a specified order (e.g., ascending or descending).

**Types:**
- **Bubble Sort:** Compares adjacent elements and swaps them if they are in the wrong order. Repeats this until the list is sorted.
- **Selection Sort:** Selects the smallest (or largest) element from the unsorted portion of the list and moves it to the beginning.
- **Insertion Sort:** Builds the final sorted list one item at a time, inserting each new element into its correct position.
- **Merge Sort:** Divides the array into halves, sorts each half, and then merges the sorted halves.
- **Quick Sort:** Chooses a 'pivot' element and partitions the array into elements less than the pivot and elements greater than the pivot. Recursively sorts the partitions.

**Real-Time Applications:**
1. **Database Management:** Sorting is crucial for efficiently organizing and querying large datasets.
2. **Web Browsers:** Sorting search results or displaying items in a preferred order.
3. **Data Analysis:** Organizing datasets for analysis or reporting.

**Example Code: (Merge Sort)**
```java
void mergeSort(int[] arr) {
    if (arr.length < 2) return;
    int mid = arr.length / 2;
    int[] left = Arrays.copyOfRange(arr, 0, mid);
    int[] right = Arrays.copyOfRange(arr, mid, arr.length);
    mergeSort(left);
    mergeSort(right);
    merge(arr, left, right);
}

void merge(int[] arr, int[] left, int[] right) {
    int i = 0, j = 0, k = 0;
    while (i < left.length && j < right.length) {
        if (left[i] <= right[j]) arr[k++] = left[i++];
        else arr[k++] = right[j++];
    }
    while (i < left.length) arr[k++] = left[i++];
    while (j < right.length) arr[k++] = right[j++];
}
```

### 2. Searching Algorithms

**Definition:** Search algorithms find a specific element or value within a dataset.

**Types:**
- **Linear Search:** Checks each element sequentially until the target is found or the end of the list is reached.
- **Binary Search:** Efficiently finds a target value in a sorted array by repeatedly dividing the search interval in half.

**Real-Time Applications:**
1. **Internet Search Engines:** Finds relevant results based on user queries.
2. **Navigation Systems:** Finds optimal routes in GPS systems.
3. **Data Retrieval:** Locates specific records in databases.

**Example Code: (Binary Search)**
```java
int binarySearch(int[] arr, int target) {
    int left = 0, right = arr.length - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target) return mid;
        if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1; // Target not found
}
```

### 3. Graph Algorithms

**Definition:** Graph algorithms solve problems related to graphs, which are collections of nodes connected by edges.

**Types:**
- **Depth-First Search (DFS):** Explores as far as possible along each branch before backtracking.
- **Breadth-First Search (BFS):** Explores all neighbors of a node before moving to the next level.
- **Dijkstra’s Algorithm:** Finds the shortest path between nodes in a graph with non-negative weights.
- **Kruskal’s Algorithm:** Finds the minimum spanning tree of a graph.

**Real-Time Applications:**
1. **Social Networks:** Analyzing relationships, detecting communities, and recommending friends.
2. **Transportation Networks:** Optimizing routes and traffic flow.
3. **Internet Routing:** Managing data packets and optimizing paths.

**Example Code: (Dijkstra's Algorithm)**
```java
import java.util.*;

class Graph {
    private final int V;
    private final List<List<Node>> adj;

    Graph(int v) {
        V = v;
        adj = new ArrayList<>();
        for (int i = 0; i < v; i++) {
            adj.add(new ArrayList<>());
        }
    }

    void addEdge(int u, int v, int w) {
        adj.get(u).add(new Node(v, w));
        adj.get(v).add(new Node(u, w));
    }

    void dijkstra(int src) {
        PriorityQueue<Node> pq = new PriorityQueue<>(Comparator.comparingInt(n -> n.cost));
        int[] dist = new int[V];
        Arrays.fill(dist, Integer.MAX_VALUE);
        pq.add(new Node(src, 0));
        dist[src] = 0;

        while (!pq.isEmpty()) {
            Node node = pq.poll();
            for (Node neighbor : adj.get(node.vertex)) {
                int newDist = dist[node.vertex] + neighbor.cost;
                if (newDist < dist[neighbor.vertex]) {
                    dist[neighbor.vertex] = newDist;
                    pq.add(new Node(neighbor.vertex, newDist));
                }
            }
        }
        System.out.println(Arrays.toString(dist));
    }

    static class Node {
        int vertex, cost;
        Node(int v, int c) {
            vertex = v;
            cost = c;
        }
    }
}
```

### 4. Dynamic Programming

**Definition:** Dynamic programming solves complex problems by breaking them down into simpler subproblems and storing the results of subproblems to avoid redundant computations.

**Types:**
- **Top-Down Approach (Memoization):** Recursively solves subproblems and stores results.
- **Bottom-Up Approach (Tabulation):** Iteratively solves subproblems and builds up the solution.

**Real-Time Applications:**
1. **Optimization Problems:** Solves problems like the knapsack problem and sequence alignment.
2. **Robotics:** Optimizes path planning and movement.

**Example Code: (Fibonacci Sequence)**
```java
int fibonacci(int n) {
    int[] dp = new int[n + 1];
    dp[0] = 0;
    dp[1] = 1;
    for (int i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];
}
```

### 5. Greedy Algorithms

**Definition:** Greedy algorithms make the locally optimal choice at each step with the hope of finding a global optimum.

**Types:**
- **Huffman Coding:** Constructs optimal prefix codes for data compression.
- **Kruskal’s Algorithm:** Finds the minimum spanning tree using a greedy approach.

**Real-Time Applications:**
1. **Huffman Coding:** Efficient data compression for files and transmission.
2. **Minimum Spanning Trees:** Network design and clustering problems.

**Example Code: (Huffman Coding)**
```java
import java.util.*;

class HuffmanNode {
    char data;
    int freq;
    HuffmanNode left, right;

    HuffmanNode(char data, int freq) {
        this.data = data;
        this.freq = freq;
        left = right = null;
    }
}

public class HuffmanCoding {
    void printCodes(HuffmanNode root, String s) {
        if (root.left == null && root.right == null) {
            System.out.println(root.data + ": " + s);
            return;
        }
        if (root.left != null) printCodes(root.left, s + '0');
        if (root.right != null) printCodes(root.right, s + '1');
    }

    HuffmanNode buildTree(Map<Character, Integer> freqMap) {
        PriorityQueue<HuffmanNode> pq = new PriorityQueue<>(Comparator.comparingInt(n -> n.freq));
        for (Map.Entry<Character, Integer> entry : freqMap.entrySet()) {
            pq.add(new HuffmanNode(entry.getKey(), entry.getValue()));
        }
        while (pq.size() > 1) {
            HuffmanNode left = pq.poll();
            HuffmanNode right = pq.poll();
            HuffmanNode node = new HuffmanNode('\0', left.freq + right.freq);
            node.left = left;
            node.right = right;
            pq.add(node);
        }
        return pq.poll();
    }
}
```

### 6. Divide and Conquer Algorithms

**Definition:** Divide and conquer algorithms break a problem into smaller subproblems, solve each subproblem independently, and then combine their solutions.

**Types:**
- **Merge Sort:** Sorts elements by dividing the list and merging sorted sublists.
- **Fast Fourier Transform (FFT):** Computes the discrete Fourier transform and its inverse efficiently.

**Real-Time Applications:**
1. **Merge Sort:** Used for sorting large datasets efficiently.
2. **Fast Fourier Transform (FFT):** Applied in signal processing and data analysis.

**Example Code: (Merge Sort)**
(See the Sorting Algorithms section for code.)

