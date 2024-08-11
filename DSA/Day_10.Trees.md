# Trees

 #### Problems : - 

- Imagine you're managing a computer system with thousands of files and directories.
- Each file represents a document, image, or program, while directories contain collections of these files.
- As the number of files and directories grows, organizing them efficiently becomes increasingly challenging.
- Without a structured organisation system, finding and managing files becomes cumbersome.
- Traditional linear data structures like arrays or linked lists struggle to represent the hierarchical relationship between files and directories.- 
- We need a more efficient way to organize and search through this vast amount of data.

#### Solution  :-  Trees 

- a hierarchical data structure perfectly suited for organizing hierarchical data like file systems.
- Trees provide a natural representation of parent-child relationships, mimicking the hierarchical structure of real-world systems.
- With trees, we can efficiently navigate through directories, search for specific files, and manage large volumes of data effectively

### Characteristics 

- Non-linear
- Hierarchical
- Ordering not important
- Has nodes similar to LL; unlike LL, where each node points to just the next node in a linear fashion, each node here points to multiple nodes

### Why Do We Need Tree DS? Here are some reasons why we need Tree DS:
- Used in routers to direct packets to their destinations
- Can be used to maintain a sorted stream of data 
- Can be used to store hierarchical data
- Can be used inside compilers to represent the structure of a program’s source code
- Can be used to implement priority queues

### Trees | Nomenclature and Properties

- Node: Contains data and the pointers to the child node
- Root: Node with no parent
- Edge: Link between the two nodes
- Leaf node: Node with no children
- Parent node: Node p said to be the parent of q if there is a path from p to q
- Child node: Any node that is not the root – a child of some node
- Level: Set of all nodes at a given depth; root considered at the level zero

![image](https://github.com/user-attachments/assets/f1a6d298-7264-4df2-ab94-dc584f6afc5e)

