## Polymorphism
- Polymorphim means having multiple forms.  
- There are two types of Polymorphism
   1. Methode Overloading (Compile time Polymorphim).
   2. Method Overriding (Run-time Polymorphism).  
- Polymorphism allows us to perform a single action in different ways.In other words, polymorphism allows you to define one interface and have multiple implementations

## Methode Overloading (Compile time Polymorphim).(Static)
- When there are multiple functions with the same name but different parameters then these functions are said to be overloaded.
- Functions can be overloaded by changes in the number of arguments or/and a change in the type of arguments.
- **Definition**: If a class has multiple methods with the same name but different parameters, it is known as method overloading.
- **Purpose**: Method overloading increases the readability of the program.

### Ways to Overload Methods in Java

1. **By changing the number of parameters**:
    ```java
    class MathOperations {
        int add(int a, int b) {
            return a + b;
        }

        int add(int a, int b, int c) {
            return a + b + c;
        }
    }
    ```

2. **By changing the parameter type**:
    ```java
    class MathOperations {
        int add(int a, int b) {
            return a + b;
        }

        double add(double a, double b) {
            return a + b;
        }
    }
    ```

### Note
- In Java, method overloading cannot be achieved by changing the return type of the method alone. The parameters must also be different.
- 
## Methode Overriding (Compile time Polymorphim). (Dynamic Method Dispatch)

- **Definition**: If a subclass (child class) has a method with the same name and parameters as a method in its superclass (parent class), it is known as method overriding.
- **Purpose**: Method overriding is used to provide a specific implementation of a method that is already defined by its superclass. It is primarily used for runtime polymorphism.

### Usage of Java Method Overriding
- To implement the method defined in a superclass with a specific behavior in the subclass.
- To achieve runtime polymorphism.

### Rules for Java Method Overriding
1. The method in the child class must have the same name as in the parent class.
2. The method must have the same parameter list as in the parent class.
3. There must be an IS-A relationship (inheritance) between the classes.

### Example of Method Overriding
```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Test {
    public static void main(String args[]) {
        Animal a = new Dog();
        a.sound();  // Output: Dog barks
    }
}
