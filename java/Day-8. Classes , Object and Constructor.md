
## Classes

A **class** in Java is a user-defined blueprint from which objects are created. It serves as a template that defines the properties (attributes) and behaviors (methods) that the objects created from the class will have.

- **Definition:** A class is a logical entity that contains methods and data.
- **Purpose:** It provides a blueprint for creating objects, which are instances of the class.

**Example:**
```java
class Car {
    // Data members (attributes)
    private int speed;

    // Methods (behaviors)
    public void drive() {
        System.out.println("The car is driving.");
    }

    public void brake() {
        System.out.println("The car is braking.");
    }

    // Getter and Setter for speed
    public int getSpeed() {
        return speed;
    }

    public void setSpeed(int speed) {
        this.speed = speed;
    }
}
```

### Properties of Classes

- **Template:** A class is a blueprint or template; it does not occupy memory by itself.
- **Components:** A class can contain:
  1. Data members (variables)
  2. Methods
  3. Constructors
  4. Nested classes
  5. Interfaces

## Objects

An **object** is an instance of a class. It represents a real-world entity and can use the attributes and methods defined in the class.

- **Instantiation:** Objects are created at runtime from a class template using the `new` keyword.
- **Memory Allocation:** Objects are allocated on the heap memory.
- **Multiple Instances:** A single class can create multiple objects, each with its own unique state.

**Example:**
```java
// Create a new Car object
Car myCar = new Car();

// Set and get the state of the object
myCar.drive();
myCar.setSpeed(50);
int currentSpeed = myCar.getSpeed();
System.out.println("Current Speed: " + currentSpeed);
```

## Constructor

A **constructor** is a special method that is called when an instance of a class is created. It initializes the newly created object and sets up initial values for its attributes.

### Rules for Constructors

1. **Name:** Constructor name must be the same as the class name.
2. **Return Type:** Constructors do not have a return type, not even `void`.
3. **Purpose:** Used exclusively for initializing the class’s attributes.
4. **Automatic Invocation:** Constructors are called automatically when an object is created.

**Note:** If a constructor parameter name matches the attribute name, the `this` keyword is used to distinguish between the parameter and the class attribute.

### Types of Constructors

1. **Default Constructor**
   - A constructor with no parameters.
   - If no constructor is defined, Java provides a default constructor implicitly.
   - If a parameterized constructor is defined, the implicit default constructor is not provided.

   **Example:**
   ```java
   class Example {
       int value;

       // Default constructor
       public Example() {
           value = 0;
       }
   }
   ```

2. **Parameterized Constructor**
   - A constructor with parameters to initialize attributes with specific values.

   **Example:**
   ```java
   class Geek {
       String name;
       int id;

       // Parameterized constructor
       Geek(String name, int id) {
           this.name = name;
           this.id = id;
       }
   }

   public class Main {
       public static void main(String[] args) {
           Geek geek1 = new Geek("Avinash", 68);
           System.out.println("GeekName: " + geek1.name + " and GeekId: " + geek1.id);
       }
   }
   ```

3. **Copy Constructor**
   - A constructor that initializes a new object using another object of the same class.

   **Example:**
   ```java
   class Person {
       private String name;
       private int age;

       // Regular constructor
       public Person(String name, int age) {
           this.name = name;
           this.age = age;
       }

       // Copy constructor
       public Person(Person other) {
           this.name = other.name;
           this.age = other.age;
       }

       @Override
       public String toString() {
           return "Person{name='" + name + "', age=" + age + "}";
       }
   }

   public class Main {
       public static void main(String[] args) {
           Person original = new Person("John", 30);
           Person copy = new Person(original);
           System.out.println("Original: " + original);
           System.out.println("Copy: " + copy);
       }
   }
   ```

**Note:** Constructors do not return values, but they return the instance of the class being created.
