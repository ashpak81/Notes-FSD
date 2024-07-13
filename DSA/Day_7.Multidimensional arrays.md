# Multidimensional Arrays in Java

## Overview

A multidimensional array in Java is an array of arrays. It allows you to create complex data structures like matrices and tables. The most common type is the two-dimensional array, but Java supports arrays of any dimension.

## Declaration and Initialization

### 1. Declaration

```java
int[][] array2D;
int[][][] array3D;
```

### 2. Initialization

You can initialize a multidimensional array at the time of declaration or afterwards.

#### At the time of declaration:

```java
int[][] array2D = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

#### After declaration:

```java
int[][] array2D = new int[3][3]; // 3x3 matrix

array2D[0][0] = 1;
array2D[0][1] = 2;
array2D[0][2] = 3;
array2D[1][0] = 4;
array2D[1][1] = 5;
array2D[1][2] = 6;
array2D[2][0] = 7;
array2D[2][1] = 8;
array2D[2][2] = 9;
```

## Accessing Elements

You can access elements of a multidimensional array using row and column indices.

```java
int value = array2D[1][2]; // Access element at row 1, column 2 (zero-based index)
System.out.println(value); // Output: 6
```

## Iterating Through Multidimensional Arrays

### 1. Using nested `for` loops:

```java
for (int i = 0; i < array2D.length; i++) {
    for (int j = 0; j < array2D[i].length; j++) {
        System.out.print(array2D[i][j] + " ");
    }
    System.out.println();
}
```

### 2. Using enhanced `for` loops:

```java
for (int[] row : array2D) {
    for (int value : row) {
        System.out.print(value + " ");
    }
    System.out.println();
}
```

## Multidimensional Array Methods

### 1. Finding the length

You can find the length of each dimension in a multidimensional array.

```java
int rows = array2D.length; // Number of rows
int columns = array2D[0].length; // Number of columns in the first row
```

### 2. Summing all elements

```java
int sum = 0;
for (int[] row : array2D) {
    for (int value : row) {
        sum += value;
    }
}
System.out.println("Sum of all elements: " + sum);
```

### 3. Transposing a 2D array

Transposing an array involves swapping its rows and columns.

```java
int[][] transpose = new int[array2D[0].length][array2D.length];

for (int i = 0; i < array2D.length; i++) {
    for (int j = 0; j < array2D[i].length; j++) {
        transpose[j][i] = array2D[i][j];
    }
}

// Print transposed array
for (int[] row : transpose) {
    for (int value : row) {
        System.out.print(value + " ");
    }
    System.out.println();
}
```

## Jagged Arrays

Java also supports jagged arrays, which are arrays of arrays where the inner arrays can have different lengths.

### Declaration and Initialization

```java
int[][] jaggedArray = new int[3][];
jaggedArray[0] = new int[]{1, 2};
jaggedArray[1] = new int[]{3, 4, 5};
jaggedArray[2] = new int[]{6, 7, 8, 9};
```

### Accessing Jagged Array Elements

```java
int value = jaggedArray[1][2]; // Access element at row 1, index 2
System.out.println(value); // Output: 5
```

## Summary

Multidimensional arrays in Java provide a powerful way to work with complex data structures. Understanding how to declare, initialize, and manipulate these arrays is crucial for solving problems that involve matrices, tables, or any multi-level data organization. Whether working with fixed-size arrays or jagged arrays, Java's flexibility in handling multidimensional arrays makes it a versatile tool for programmers.
```
