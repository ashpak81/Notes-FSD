# Classes
-  Classes is a user-defined blueprint from which objects are created.
-  It is a logical entity that contains methods and data.
-  It is a template or blueprint that defines the properties and behavior of objects.
-  For example, Student is a class while a particular student named Ravi is an object.
### Properties of Classes
- Class is not a real-world entity. It is just a template or blueprint or prototype from which objects are created.
- Class does not occupy memory.
- Class is a group of variables of different data types and a group of methods.
- A Class in Java can contain :
  1. Data member
  2. Method
  3. Constructor
  4. Nested Class
  5. Interface
- To create a class, you use the keyword **class**. For example, the following code creates a class named Car:
```
  class Car {
  // Methods
  public void drive() {
    System.out.println("The car is driving.");
  }

  public void brake() {
    System.out.println("The car is braking.");
  }

  // Variables
  private int speed;

  public int getSpeed() {
    return speed;
  }

  public void setSpeed(int speed) {
    this.speed = speed;
  }
}
```

# Object
- An object in Java is a basic unit of Object-Oriented Programming and represents real-life entities.
- Objects are the instances of a class that are created to use the attributes and methods of a class.
- **Note: When we create an object which is a non primitive data type, it’s always allocated on the heap memory**
- **One classes can have many object and every object have differant memory.**
- Objects are created at runtime from templates, also known as classes. In Java, an object is created using the keyword new.
- Example :
```
  // Create a new Car object
Car BMW = new Car();

// Set the state of the object
BMW.drive();
BMW.setSpeed(50);
BMW.getSpeed();

// Call the methods of the object
myDog.drive();
myDog.break();
```

# Constructor
- A constructor is a block of codes similar to the method. It is called when an instance of the class is created.
- A constructor is a special type of method that is used to initialize attributes of class. 
- At the time of calling constructor, memory for the object is allocated in the memory.
  
- rules while creating constuctor
  1. Constructor name is same as class name.
  2. Constructor don't have datatype and return type.
  3. Constructor is used only for initialization of attributes of the class.
  4. Constructor is called automatically when the object is created.
     
- **Note** whenever constructor parameter name same as class attribute name used **this** keyword.

- There are three types of Constructor
  1. Default Constructor.
  2. Parameterized Constructor.
  3. Copy Constructor.
### Defailt Constructor : 
  - A constructor that has no parameters is known as default the constructor.
  - A default constructor is invisible. And if we write a constructor with no arguments, the compiler does not create a default constructor.
  - It is taken out. It is being overloaded and called a parameterized constructor. The default constructor changed into the parameterized constructor. But Parameterized constructor can’t change the default constructor.
  - The default constructor can be implicit or explicit. If we don’t define explicitly, we get an implicit default constructor.
  - If we manually write a constructor, the implicit one is overridded.
### Parameterized Constructor :
  - A constructor that has parameters is known as parameterized constructor.
  - If we want to initialize fields of the class with our own values, then use a parameterized constructor.
  - Example :
```
    // Java Program for Parameterized Constructor
import java.io.*;
class Geek {
    // data members of the class.
    String name;
    int id;
    Geek(String name, int id)
    {
        this.name = name;
        this.id = id;
    }
}
class GFG {
    public static void main(String[] args)
    {
        // This would invoke the parameterized constructor.
        Geek geek1 = new Geek("Avinash", 68);
        System.out.println("GeekName :" + geek1.name
                           + " and GeekId :" + geek1.id);
    }
  }
```
- Note : - Remember: Does constructor return any value?
```
  There are no “return value” statements in the constructor, but the constructor returns the current class instance.
  We can write ‘return’ inside a constructor.
```
