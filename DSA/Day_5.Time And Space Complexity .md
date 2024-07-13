# Time and Space Complexity

## Time Complexity

Time complexity is a measure of the amount of time an algorithm takes to run as a function of the length of its input. It is typically expressed using Big O notation, which describes the upper bound of the algorithm's running time.

### Types of Time Complexity

1. **Best Time Complexity (Ω - Omega)**
   - Represents the minimum time required for the best-case scenario of an algorithm.

2. **Average Time Complexity (θ - Theta)**
   - Represents the average time required for an algorithm across all possible inputs.

3. **Worst Time Complexity (O - Big O)**
   - Represents the maximum time required for the worst-case scenario of an algorithm.

4. **Logarithmic Time Complexity (O(log n))**
   - Represents algorithms that reduce the problem size by a constant fraction with each step, such as binary search.

### How to Determine Time Complexity

#### 1. Constant Time Complexity (O(1))

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
- **Explanation**: The operations here (assigning `x`, printing `x`, and iterating through the array) are not dependent on the size of the input (`n`). Thus, the time complexity remains constant.

#### 2. Linear Time Complexity (O(n))

```java
int x = 10;
int n = sc.nextInt();
System.out.println(x);
int[] arr = new int[n];
n = arr.length;
for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);
}
```
- **Time Complexity**: O(n)
- **Explanation**: The time taken increases linearly with the size of the input (`n`) due to the single loop iterating through the array.

#### 3. Logarithmic Time Complexity (O(log n))

```java
int n = sc.nextInt();
int count = 0;
while (n > 1) {
    n = n / 2;
    count++;
}
```
- **Time Complexity**: O(log n)
- **Explanation**: This example shows a logarithmic time complexity where the problem size (`n`) is halved with each iteration (binary division). Algorithms like binary search exhibit logarithmic time complexity.

#### 4. Quadratic Time Complexity (O(n^2))

```java
int x = 10;
int n = sc.nextInt();
System.out.println(x);
int[] arr = new int[n];
n = arr.length;
for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);
    for (int j = 0; j < n; j++) {
        System.out.println(arr[j]);
    }
}
```
- **Time Complexity**: O(n^2)
- **Explanation**: This nested loop structure causes the time complexity to grow quadratically with the input size `n`, as each element is processed multiple times.

#### 5. Polynomial Time Complexity (O(n^m))

```java
int x = 10;
int n = sc.nextInt();
System.out.println(x);
int[] arr = new int[n];
n = arr.length;
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
- **Time Complexity**: O(n^m)
- **Explanation**: This example demonstrates `m` nested loops, where each loop iterates up to `n` times. Thus, the time complexity is polynomial, reflecting the combined effect of multiple nested loops.

## Space Complexity

Space complexity is a measure of the amount of memory space an algorithm requires as a function of the length of its input. It also uses Big O notation to describe the upper bound of memory usage by the algorithm.

### How to Determine Space Complexity

- Space complexity considers the total space used by the algorithm, including auxiliary space used by recursion stacks, data structures, etc.

## Summary

Understanding time and space complexity helps in analyzing and optimizing algorithms. Time complexity quantifies the efficiency of an algorithm in terms of its running time, while space complexity measures its memory usage. Both are crucial for evaluating algorithm performance and scalability.
```
