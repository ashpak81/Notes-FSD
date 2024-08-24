
# Time and Space Complexity

## Time Complexity

Time complexity measures the time an algorithm takes to run relative to the size of its input, usually expressed using Big O notation. This helps in understanding how the runtime of an algorithm increases as the input size grows.

### Types of Time Complexity

1. **Best Time Complexity (Ω - Omega)**
   - Represents the minimum time required for the best-case scenario of an algorithm. It shows the least time the algorithm can take for any possible input.

2. **Average Time Complexity (θ - Theta)**
   - Represents the average time required for an algorithm over all possible inputs. This provides a more realistic view of an algorithm’s performance.

3. **Worst Time Complexity (O - Big O)**
   - Represents the maximum time required for the worst-case scenario of an algorithm. It provides an upper bound on the running time.

4. **Logarithmic Time Complexity (O(log n))**
   - Describes algorithms that reduce the problem size by a constant fraction each step, such as binary search.

### How to Determine Time Complexity

#### 1. Constant Time Complexity (O(1))
Operations that take the same amount of time regardless of the input size.

**Example**:
```java
int x = 10;
System.out.println(x);
int[] arr = {1, 2, 3, 4};
int n = arr.length;
for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);
}
```
- **Time Complexity**: O(1)
- **Explanation**: Printing `x` and accessing array elements involves constant time operations. The loop through the array is separate, but its complexity depends on `n`, making this part O(n).

#### 2. Linear Time Complexity (O(n))
Operations that scale linearly with the input size `n`.

**Example**:
```java
int x = 10;
int n = sc.nextInt();
System.out.println(x);
int[] arr = new int[n];
for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);
}
```
- **Time Complexity**: O(n)
- **Explanation**: The time taken increases linearly with the size of the array due to the single loop iterating `n` times.

#### 3. Logarithmic Time Complexity (O(log n))
Operations that halve the problem size with each step, such as binary search.

**Example**:
```java
int n = sc.nextInt();
int count = 0;
while (n > 1) {
    n = n / 2;
    count++;
}
```
- **Time Complexity**: O(log n)
- **Explanation**: Each iteration divides `n` by 2, so the number of iterations grows logarithmically with `n`.

#### 4. Quadratic Time Complexity (O(n^2))
Operations with nested loops, where the time grows quadratically with the input size.

**Example**:
```java
int x = 10;
int n = sc.nextInt();
System.out.println(x);
int[] arr = new int[n];
for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);
    for (int j = 0; j < n; j++) {
        System.out.println(arr[j]);
    }
}
```
- **Time Complexity**: O(n^2)
- **Explanation**: Two nested loops each running `n` times result in a quadratic growth of the runtime.

#### 5. Polynomial Time Complexity (O(n^m))
Operations involving multiple nested loops or recursive calls where the time grows polynomially with the input size.

**Example**:
```java
int x = 10;
int n = sc.nextInt();
System.out.println(x);
int[] arr = new int[n];
for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);
    for (int j = 0; j < n; j++) {
        System.out.println(arr[j]);
    }
    for (int k = 0; k < n; k++) {
        System.out.println(arr[k]);
    }
}
```
- **Time Complexity**: O(n^3)
- **Explanation**: Three nested loops, each iterating `n` times, result in a cubic growth of the runtime.

## Space Complexity

Space complexity measures the amount of memory space an algorithm requires relative to the size of its input. It includes both the space required for the algorithm’s variables and any additional space used by data structures or recursion.

### How to Determine Space Complexity

1. **Auxiliary Space**:
   - Space used by extra data structures (arrays, hash tables, etc.) and recursion stacks.

2. **Space Complexity Formula**:
   - Sum the space required for all variables and data structures used, including the space for recursive calls.

### Examples

#### 1. Constant Space Complexity (O(1))
Algorithms that use a fixed amount of space regardless of the input size.

**Example**:
```java
public class ConstantSpace {
    public static void main(String[] args) {
        int x = 10;
        int y = 20;
        int z = x + y;
        System.out.println(z);
    }
}
```
- **Space Complexity**: O(1)
- **Explanation**: Only a few variables are used, and their space does not depend on the input size.

#### 2. Linear Space Complexity (O(n))
Algorithms that use additional space proportional to the input size.

**Example**:
```java
public class LinearSpace {
    public static void main(String[] args) {
        int n = 5;
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = i;
        }
    }
}
```
- **Space Complexity**: O(n)
- **Explanation**: The space required for the array grows linearly with `n`.

#### 3. Space Complexity with Recursion

**Example: Factorial Using Recursion**
```java
public class Factorial {
    public static int factorial(int n) {
        if (n == 0) { // Base case
            return 1;
        } else { // Recursive case
            return n * factorial(n - 1);
        }
    }

    public static void main(String[] args) {
        System.out.println("Factorial of 5 is: " + factorial(5)); // Output: 120
    }
}
```
- **Space Complexity**: O(n)
- **Explanation**: Each recursive call adds a new frame to the call stack, so the space complexity is proportional to the recursion depth.

## Summary

Understanding time and space complexity is crucial for evaluating and optimizing algorithms. Time complexity helps in analyzing how an algorithm's runtime scales with input size, while space complexity measures its memory usage. By mastering these concepts, you can design more efficient and scalable algorithms.
