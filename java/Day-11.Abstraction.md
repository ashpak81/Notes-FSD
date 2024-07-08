## Abstraction
- Abstraction is a fundamental concept in object-oriented programming (OOP) that allows you to focus on the essential features of an object while hiding the unnecessary details of its implementation.
- In Java, abstraction is achieved using two key constructs:
    
#### 1. Abstract Classes:
        - An abstract class is a class that cannot be instantiated (you cannot create objects from it directly).
        - It is declared using the abstract keyword.
        - An abstract class can contain abstract methods (methods without a body) and concrete methods (methods with a body).
        - Classes that inherit from an abstract class must provide implementations for all its abstract methods.
```
        abstract class Animal { // Abstract class
    public abstract void makeSound(); // Abstract method

    public void eat() { // Concrete method
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal { // Concrete subclass
    public void makeSound() { // Implementing abstract method
        System.out.println("Woof!");
    }
}

// Usage
Dog myDog = new Dog();
myDog.makeSound(); // Output: Woof!
myDog.eat(); // Output: Animal is eating
```
#### 2. Interfaces:
- An interface is a contract that defines a set of methods that a class must implement.
- It is declared using the interface keyword.
- All methods in an interface are implicitly public and abstract (before Java 8).
- A class can implement multiple interfaces.
```
  interface Shape {
    double getArea(); // Abstract method
    double getPerimeter(); // Abstract method
}

class Circle implements Shape {
    // ... Implementation of getArea() and getPerimeter() methods
}

class Rectangle implements Shape {
    // ... Implementation of getArea() and getPerimeter() methods
}
```

