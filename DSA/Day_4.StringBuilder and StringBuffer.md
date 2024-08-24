
## StringBuilder and StringBuffer in Java

### Overview
Both `StringBuilder` and `StringBuffer` are mutable classes in Java designed for creating and manipulating sequences of characters. Unlike `String`, which is immutable, these classes allow modifications to the character sequences. Their main differences lie in thread safety and performance:

- **Synchronization**:
  - `StringBuffer` is synchronized and thread-safe, suitable for multithreaded environments.
  - `StringBuilder` is not synchronized and is intended for single-threaded scenarios.

- **Performance**:
  - `StringBuilder` typically has better performance than `StringBuffer` because it lacks synchronization overhead.

- **Use Cases**:
  - Use `StringBuilder` for performance-critical, single-threaded applications.
  - Use `StringBuffer` when working in a multithreaded environment where thread safety is a concern.

---

### StringBuilder

**What is it?**
`StringBuilder` is a mutable sequence of characters that allows you to efficiently manipulate strings. It is more performant compared to using the `+` operator for string concatenation.

**Key Advantages**:
- **Efficiency**: More efficient for concatenations and string manipulations compared to using `String` directly due to reduced overhead.
- **Flexibility**: Provides a rich set of methods for modifying the character sequence.

**Commonly Used Methods**:
- **`append(String str)`**: Appends the specified string to the end of the `StringBuilder`.
  ```java
  sb.append(" World"); // Appends " World"
  ```
- **`insert(int offset, String str)`**: Inserts the specified string at the specified index.
  ```java
  sb.insert(5, ", "); // Inserts ", " at index 5
  ```
- **`delete(int start, int end)`**: Deletes characters from `start` to `end`.
  ```java
  sb.delete(5, 7); // Deletes characters from index 5 to 7
  ```
- **`replace(int start, int end, String str)`**: Replaces characters from `start` to `end` with the specified string.
  ```java
  sb.replace(5, 7, "X"); // Replaces characters from index 5 to 7 with "X"
  ```
- **`reverse()`**: Reverses the character sequence.
  ```java
  sb.reverse(); // Reverses the content of sb
  ```
- **`toString()`**: Converts the `StringBuilder` object to a `String`.
  ```java
  String str = sb.toString(); // Converts to String
  ```

**Constructors**:
- **`StringBuilder()`**: Creates an empty `StringBuilder` with an initial capacity of 16 characters.
  ```java
  StringBuilder sb = new StringBuilder();
  ```
- **`StringBuilder(int capacity)`**: Creates an empty `StringBuilder` with the specified capacity.
  ```java
  StringBuilder sb = new StringBuilder(50);
  ```
- **`StringBuilder(String str)`**: Creates a `StringBuilder` initialized with the contents of the specified string.
  ```java
  StringBuilder sb = new StringBuilder("Initial");
  ```

**Example**:
```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" ");
sb.append("World");
sb.insert(5, ",");
System.out.println(sb.toString()); // Output: Hello, World
```

---

### StringBuffer

**Overview**:
`StringBuffer` is similar to `StringBuilder` but with added thread safety due to its synchronized methods. It is used in scenarios where multiple threads might modify the same sequence of characters.

**Key Features**:
- **Mutable**: Allows modification of the character sequence.
- **Thread-safe**: Provides synchronization to ensure safe use in multithreaded environments.
- **Growable**: Automatically expands its capacity as needed.

**Commonly Used Methods**:
- **`append(String str)`**: Appends the specified string to the end of the `StringBuffer`.
  ```java
  sb.append(" World"); // Appends " World"
  ```
- **`insert(int offset, String str)`**: Inserts the specified string at the specified index.
  ```java
  sb.insert(5, " "); // Inserts " " at index 5
  ```
- **`delete(int start, int end)`**: Deletes characters from `start` to `end`.
  ```java
  sb.delete(5, 7); // Deletes characters from index 5 to 7
  ```
- **`replace(int start, int end, String str)`**: Replaces characters from `start` to `end` with the specified string.
  ```java
  sb.replace(5, 7, "X"); // Replaces characters from index 5 to 7 with "X"
  ```
- **`reverse()`**: Reverses the character sequence.
  ```java
  sb.reverse(); // Reverses the content of sb
  ```
- **`toString()`**: Converts the `StringBuffer` object to a `String`.
  ```java
  String str = sb.toString(); // Converts to String
  ```

**Constructors**:
- **`StringBuffer()`**: Creates an empty `StringBuffer` with an initial capacity of 16 characters.
  ```java
  StringBuffer sb = new StringBuffer();
  ```
- **`StringBuffer(int capacity)`**: Creates an empty `StringBuffer` with the specified capacity.
  ```java
  StringBuffer sb = new StringBuffer(50);
  ```
- **`StringBuffer(String str)`**: Creates a `StringBuffer` initialized with the contents of the specified string.
  ```java
  StringBuffer sb = new StringBuffer("Initial");
  ```

**Example**:
```java
StringBuffer sb = new StringBuffer("Hello");
sb.append(" World");
sb.insert(5, " ");
System.out.println(sb); // Output: Hello World
```

---

### Summary

- **`StringBuilder`**: Preferred for single-threaded environments due to its better performance. Suitable for scenarios where the string is frequently modified.
- **`StringBuffer`**: Thread-safe and used in multithreaded contexts where synchronization is necessary. It offers similar functionality to `StringBuilder` but with synchronization overhead.
