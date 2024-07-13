# StringBuilder and StringBuffer in Java

## Overview
StringBuilder and StringBuffer are both mutable classes that provide an alternative to the immutable `String` class by creating mutable sequences of characters. They are similar in function but have key differences:

- **Synchronization**: 
  - `StringBuffer` is synchronized and thread-safe, making it suitable for use in multithreaded environments.
  - `StringBuilder` is not synchronized and should be used in single-threaded environments.

- **Speed**: 
  - `StringBuilder` is faster than `StringBuffer`.

- **Use Cases**: 
  - `StringBuilder` is preferred for single-threaded programs and efficient string manipulation.
  - `StringBuffer` is better for thread safety in multithreaded environments.

## StringBuilder

### What is it?
A mutable sequence of characters, meaning you can modify its content after creation, unlike Strings which are immutable. It is used for dynamically building strings, especially when performance is a concern.

### Key Advantages
- **Efficiency**: 
  Appending to a `StringBuilder` is much faster than concatenating Strings with the `+` operator, especially for a large number of operations.
- **Flexibility**: 
  Offers various methods for inserting, deleting, replacing, and appending characters or substrings.

### Commonly Used Methods
- `append(String str)`: Appends the specified string to the end of the sequence.
- `insert(int offset, String str)`: Inserts the specified string at the specified index.
- `delete(int start, int end)`: Deletes characters from the sequence.
- `replace(int start, int end, String str)`: Replaces characters in the sequence with the specified string.
- `reverse()`: Reverses the sequence of characters.
- `toString()`: Converts the `StringBuilder` object to a `String` object.

### Constructors
- `StringBuilder()`: Creates an empty `StringBuilder` with an initial capacity of 16 characters.
- `StringBuilder(int capacity)`: Creates an empty `StringBuilder` with the specified capacity.
- `StringBuilder(String str)`: Creates a `StringBuilder` initialized with the contents of the specified string.

### Example
```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" ");
sb.append("World");
sb.insert(5, ",");
System.out.println(sb.toString()); // Output: Hello, World
```

# StringBuffer in Java

## Overview
`StringBuffer` is a mutable sequence of characters that can be modified after creation. It provides methods for appending, inserting, deleting, and modifying characters within the sequence. `StringBuffer` is thread-safe, meaning it can be safely used in multithreaded environments.

## Key Features
- **Mutable**: 
  Can be modified without creating a new object, which is more efficient for string manipulation operations.
- **Thread-safe**: 
  Synchronized methods ensure data integrity when accessed by multiple threads.
- **Growable**: 
  Automatically expands its capacity as needed to accommodate new characters.

## Commonly Used Methods
- `append(String str)`: Appends the given string to the end of the `StringBuffer`.
- `insert(int offset, String str)`: Inserts the given string at the specified offset within the `StringBuffer`.
- `delete(int start, int end)`: Deletes characters from the `StringBuffer` between the specified start and end indices.
- `replace(int start, int end, String str)`: Replaces characters within the specified range with the given string.
- `reverse()`: Reverses the character sequence within the `StringBuffer`.
- `toString()`: Converts the `StringBuffer` object into a `String` object.

## Constructors
- `StringBuffer()`: Creates an empty `StringBuffer` with an initial capacity of 16 characters.
- `StringBuffer(int capacity)`: Creates an empty `StringBuffer` with the specified initial capacity.
- `StringBuffer(String str)`: Creates a `StringBuffer` with the contents of the given `String`.

## Example
```java
StringBuffer sb = new StringBuffer("Hello");
sb.append(" World");
sb.insert(5, " ");
System.out.println(sb); // Output: Hello World
