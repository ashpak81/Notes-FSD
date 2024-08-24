## Loops in Java

Loops in Java are used to repeatedly execute a block of code as long as a specified condition evaluates to `true`. There are three primary types of loops in Java: `for`, `while`, and `do-while`.

### For Loop

The `for` loop is commonly used to iterate over a range of values or through a collection of data, such as an array or a list. It is particularly useful when the number of iterations is known beforehand.

**Syntax:**
```java
for (initialization; condition; increment) {
    // Code to be executed
}
```

- **Initialization:** Initializes a loop control variable.
- **Condition:** Evaluated before each iteration; the loop continues as long as this condition is `true`.
- **Increment:** Updates the loop control variable after each iteration.

**Example:**
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

### While Loop

The `while` loop is used to execute a block of code as long as a specified condition remains `true`. It is ideal when the number of iterations is not known in advance.

**Syntax:**
```java
while (condition) {
    // Code to be executed
}
```

- **Condition:** Evaluated before each iteration; if `true`, the code block is executed.

**Example:**
```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

### Do-While Loop

The `do-while` loop is similar to the `while` loop, but it guarantees that the code block will be executed at least once. The condition is evaluated after the code block is executed.

**Syntax:**
```java
do {
    // Code to be executed
    // Update condition if necessary
} while (condition);
```

- **Condition:** Evaluated after the code block is executed; the loop continues as long as this condition is `true`.

**Example:**
```java
int i = 0;
do {
    System.out.println(i);
    i++;
} while (i < 5);
```
