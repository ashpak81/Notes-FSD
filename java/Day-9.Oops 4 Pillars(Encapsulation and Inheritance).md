

## The Four Pillars of OOP

### 1. Encapsulation

**Encapsulation** is the practice of bundling data (attributes) and methods (functions) that operate on that data into a single unit, known as a class. The main goal is to restrict direct access to some of an object's components, which can prevent the accidental modification of data.

- **Purpose:** Protects the internal state of the object and ensures that only authorized methods can access or modify it.
- **Implementation:** Achieved by making the class attributes private and providing public getter and setter methods to access and update these attributes.

**Steps to Achieve Encapsulation:**
1. Declare the data members (variables) as `private`.
2. Provide public getter and setter methods to access and modify the private data.

**Example:**
```java
public class Car {
    // Private variables
    private int speed;
    private int fuel;

    // Getter and setter for speed
    public int getSpeed() {
        return speed;
    }

    public void setSpeed(int speed) {
        this.speed = speed;
    }

    // Getter and setter for fuel
    public int getFuel() {
        return fuel;
    }

    public void setFuel(int fuel) {
        this.fuel = fuel;
    }
}
```

**Advantages of Encapsulation:**
- **Control Over Data:** Ensures controlled access to data through getter and setter methods.
- **Data Hiding:** Prevents unauthorized access to internal data by making it private.
- **Easy to Test:** Simplifies testing by isolating data and methods within classes.

### 2. Inheritance

**Inheritance** is a mechanism by which one class (the subclass or child class) acquires the properties and behaviors of another class (the superclass or parent class). This allows for code reuse and the extension of existing functionality.

- **Keyword:** `extends`
- **Purpose:** Promotes code reuse and establishes a natural hierarchy between classes.

**Types of Inheritance:**
1. **Single Inheritance:** A class inherits from one superclass.
   ```java
   class Animal {
       void eat() {
           System.out.println("Eating");
       }
   }

   class Dog extends Animal {
       void bark() {
           System.out.println("Barking");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Dog dog = new Dog();
           dog.eat();  // Inherited method
           dog.bark(); // Method of Dog class
       }
   }
   ```

2. **Multilevel Inheritance:** A class inherits from another derived class, forming a chain.
   ```java
   class Animal {
       void eat() {
           System.out.println("Eating");
       }
   }

   class Dog extends Animal {
       void bark() {
           System.out.println("Barking");
       }
   }

   class Puppy extends Dog {
       void play() {
           System.out.println("Playing");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Puppy puppy = new Puppy();
           puppy.eat();  // Inherited from Animal
           puppy.bark(); // Inherited from Dog
           puppy.play(); // Method of Puppy class
       }
   }
   ```

3. **Hierarchical Inheritance:** Multiple classes inherit from a single superclass.
   ```java
   class Animal {
       void eat() {
           System.out.println("Eating");
       }
   }

   class Dog extends Animal {
       void bark() {
           System.out.println("Barking");
       }
   }

   class Cat extends Animal {
       void meow() {
           System.out.println("Meowing");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Dog dog = new Dog();
           Cat cat = new Cat();

           dog.eat();  // Inherited from Animal
           dog.bark(); // Method of Dog class

           cat.eat();  // Inherited from Animal
           cat.meow(); // Method of Cat class
       }
   }
   ```

4. **Multiple Inheritance (via Interfaces):** Java does not support multiple inheritance through classes but allows it through interfaces.
   ```java
   interface Animal {
       void eat();
   }

   interface Bird {
       void fly();
   }

   class Bat implements Animal, Bird {
       public void eat() {
           System.out.println("Eating");
       }

       public void fly() {
           System.out.println("Flying");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Bat bat = new Bat();
           bat.eat(); // Method from Animal interface
           bat.fly(); // Method from Bird interface
       }
   }
   ```

5. **Hybrid Inheritance:** Combines two or more types of inheritance. Typically involves a mix of single, multilevel, and interface inheritance.
   ```java
   interface Animal {
       void eat();
   }

   interface Bird {
       void fly();
   }

   class Dog implements Animal {
       public void eat() {
           System.out.println("Eating");
       }

       void bark() {
           System.out.println("Barking");
       }
   }

   class FlyingDog extends Dog implements Bird {
       public void fly() {
           System.out.println("Flying");
       }
   }

   public class Main {
       public static void main(String[] args) {
           FlyingDog flyingDog = new FlyingDog();
           flyingDog.eat();  // From Dog class implementing Animal
           flyingDog.bark(); // From Dog class
           flyingDog.fly();  // From Bird interface
       }
   }
   ```

### 3. Abstraction

**Abstraction** is the concept of hiding the complex implementation details and showing only the necessary features of an object. It allows focusing on what an object does instead of how it does it.

- **Purpose:** To simplify complex systems by breaking them down into manageable parts and focusing on the essential characteristics.
- **Implementation:** Achieved using abstract classes and interfaces.

**Example:**
```java
abstract class Animal {
    abstract void makeSound(); // Abstract method (does not have a body)

    void sleep() {
        System.out.println("Sleeping");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Barking");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound(); // Implementation of abstract method
        dog.sleep();     // Regular method
    }
}
```

### 4. Polymorphism

**Polymorphism** means "many shapes" and allows objects to be treated as instances of their parent class rather than their actual class. It provides a way to perform a single action in different forms.

- **Purpose:** Enables methods to perform different tasks based on the object that is calling them, enhancing flexibility and maintainability.
- **Types:**
  1. **Compile-time Polymorphism (Method Overloading):** Multiple methods with the same name but different parameters.
  2. **Runtime Polymorphism (Method Overriding):** A subclass provides a specific implementation of a method that is already defined in its superclass.

**Examples:**

1. **Method Overloading (Compile-time Polymorphism):**
   ```java
   class Printer {
       void print(int i) {
           System.out.println("Printing integer: " + i);
       }

       void print(String s) {
           System.out.println("Printing string: " + s);
       }
   }

   public class Main {
       public static void main(String[] args) {
           Printer printer = new Printer();
           printer.print(5);       // Calls print(int)
           printer.print("Hello"); // Calls print(String)
       }
   }
   ```

2. **Method Overriding (Runtime Polymorphism):**
   ```java
   class Animal {
       void makeSound() {
           System.out.println("Animal sound");
       }
   }

   class Dog extends Animal {
       void makeSound() {
           System.out.println("Barking");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Animal myAnimal = new Dog(); // Upcasting
           myAnimal.makeSound();       // Calls Dog's makeSound() method
       }
   }
   ```

## The `super` Keyword

The `super` keyword in Java is used to refer to the immediate parent class object and its members (methods, constructors, and fields). It is particularly useful in inheritance to access superclass methods and constructors.

### Usage of `super` Keyword

1. **Calling a Superclass Constructor:**
   - Used to invoke the constructor of the superclass from the subclass.
   ```java
   class Animal {
       Animal() {
           System.out.println("Animal constructor called");
       }
   }

   class Dog extends Animal {
       Dog() {
           super(); // Calls the constructor of Animal
           System.out.println("Dog constructor called");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Dog dog = new Dog();
       }
   }
   ```

2. **Accessing a Superclass Method:**
   - Used to call an overridden method from the superclass.
   ```java
   class Animal {
       void eat() {
           System.out.println("Animal is eating");
       }
   }

   class Dog extends Animal {
       void eat() {
           System.out.println("Dog is eating");
       }

       void display() {
           super.eat(); // Calls the eat method of Animal
           eat();       // Calls the eat method of Dog
       }
   }

   public class Main {
       public static void main(String[] args) {
           Dog

 dog = new Dog();
           dog.display();
       }
   }
   ```

3. **Accessing a Superclass Field:**
   - Used to access hidden fields of the superclass.
   ```java
   class Animal {
       String color = "white";
   }

   class Dog extends Animal {
       String color = "black";

       void display() {
           System.out.println("Dog color: " + color);         // Refers to Dog's color
           System.out.println("Animal color: " + super.color); // Refers to Animal's color
       }
   }

   public class Main {
       public static void main(String[] args) {
           Dog dog = new Dog();
           dog.display();
       }
   }
   ```

### Important Points to Remember about `super` Keyword:
- **Constructor Invocation:** `super()` must be the first statement in the subclass constructor.
- **Method and Field Access:** `super` can only be used to access members from the immediate superclass.
- **Static Context:** `super` cannot be used in a static context as it pertains to instance-level data.
