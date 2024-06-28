# What is Arrays ?
- Arrays is a **Data Structure that stores a fixed-size sequential collection of elements of the same type**.
- Each element in an array is identified by an index, which represents its position in the array.
# Why used Array ?
- Arrays are widely used because they allow efficient access to elements based on their index.
  This is useful when we need to store large amounts of data and process them efficiently. Arrays are also used for sorting, searching, accessing, and manipulating data.
- **Efficient Access** : Elements in an array can be accessed in constant time O(1) using their index, which makes array access very efficient.
- **Sequential Storage** : Elements in an array are stored sequentially in memory, making it straightforward to iterate over them in order.
- **Predictable Performance** : Arrays provide predictable performance characteristics for access, which can be important in time-sensitive applications.
# how we can used Array ?
- arrays are declared by specifying the element type followed by square brackets ([]).
- Here are Syntax of different ways to declare and use arrays:
  ```
    Syntax to Declare an Array in Java
        dataType[] arr; (or)  
        dataType []arr; (or)  
        dataType arr[];  
     Instantiation of an Array in Java
        arrayRefVar=new datatype[size];
     We can directly used array like
      datatype[] arr = {value1,value2,value3,.....,valueN};
  ```
# Example Of array
- Here are examples of different ways to declare and use arrays:

 ``` // Declaring an array of integers
int[] numbers = new int[5];  // creates an array with 5 elements

// Initializing elements of the array
numbers[0] = 10;
numbers[1] = 20;
numbers[2] = 30;
numbers[3] = 40;
numbers[4] = 50;

// Accessing elements of the array
System.out.println(numbers[2]);  // prints 30

// Arrays can also be initialized with values directly
String[] names = {"Alice", "Bob", "Charlie"};

// Accessing elements of the array using a loop
for (int i = 0; i < names.length; i++) {
    System.out.println("Name at index " + i + ": " + names[i]);
}
```
 
   
    
