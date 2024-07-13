# Recursion in Java

## Overview
Recursion is a programming technique where a method calls itself to solve a problem. It is a powerful tool for solving problems that can be broken down into smaller, similar subproblems.

## Key Concepts

### Base Case
- The condition under which the recursive method stops calling itself. Without a base case, the recursion would continue indefinitely, leading to a stack overflow error.

### Recursive Case
- The part of the method where the recursion occurs. This typically involves calling the same method with a modified argument, moving towards the base case.

## Important Points
- When a function calls itself inside its call, it is called recursion.
- Recursion is used to solve complex problems by dividing a bigger problem into smaller, more manageable problems.
- Recursion uses the call stack to keep track of recursive function calls.
- It takes more memory due to the storage of function call information on the stack.
- The approach of recursion is top-down (breaking down the problem) and then bottom-up (combining solutions to subproblems).
- An improved version of recursion is Dynamic Programming (DP), which optimizes recursive solutions by storing the results of subproblems to avoid redundant calculations.

## Example: Factorial
The factorial of a number `n` (denoted as `n!`) is the product of all positive integers less than or equal to `n`. It is defined as:
- `n! = n * (n - 1)!`
- `0! = 1`

### Code Example
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
