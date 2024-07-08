## Polymorphism
- Polymorphim means having multiple forms.  
- There are two types of Polymorphism
   1. Methode Overloading (Compile time Polymorphim).
   2. Method Overriding (Run-time Polymorphism).  
- Polymorphism allows us to perform a single action in different ways.In other words, polymorphism allows you to define one interface and have multiple implementations

### 1. Methode Overloading (Compile time Polymorphim).(Static)
- When there are multiple functions with the same name but different parameters then these functions are said to be overloaded.
- Functions can be overloaded by changes in the number of arguments or/and a change in the type of arguments.
```
class Helper {

    // Method with 2 integer parameters
    static int Multiply(int a, int b)
    {
        // Returns product of integer numbers
        return a * b;
    }

    // Method 2
    // With same name but with 2 double parameters
    static double Multiply(double a, double b)
    {
        // Returns product of double numbers
        return a * b;
    }
}

// Class 2
// Main class
class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Calling method by passing
        // input as in arguments
        System.out.println(Helper.Multiply(2, 4));
        System.out.println(Helper.Multiply(5.5, 6.3));
    }
}
```
### 1. Methode Overriding (Compile time Polymorphim). (Dynamic Method Dispatch)
- Runtime polymorphism, also known as dynamic method dispatch in Java, is a process where the method call to an overridden method is resolved at runtime rather than at compile time.
- How it works:
  1. Inheritance:
    - You need a base class and a derived class that inherits from the base class.
  2. Method Overriding:
    - The derived class must override a method that is already present in the base class. This means having the same method signature (name, parameters, and return type) in both classes, but with different implementations in the derived class.
  3. Upcasting:  
    - Create an object of the derived class and store it in a reference variable of the base class type. This is called upcasting.
 ```
class Animal {
    public void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    public void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myAnimal = new Dog(); // Upcasting
        myAnimal.sound(); // Output: Dog barks

        myAnimal = new Cat(); // Upcasting
        myAnimal.sound(); // Output: Cat meows
    }
}
```
