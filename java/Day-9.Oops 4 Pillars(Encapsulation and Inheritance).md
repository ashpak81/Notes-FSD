# Oops 4 Pillars
1. Encapsulation :- Security.
2. Inheritance   :- Code Reusability.
3. Abstraction   :-  Show Important Data.
4. Polymorphism  :-  one name many form.
## Encapsulation
- Eapsulation is a fundamental concept in object-oriented programming that refers to the bundling of data(variable) and methods that operate on that data within a single unit, which is called a class in Java.
- The main purpose of encapsulation is to protect the data from being accessed or modified by unauthorized code.
- This is achieved by making the data members of a class private and providing public methods to access and modify them.
  
**Stpes to Achive Encapsulation**
1. declare a variable private.
2. declare the setter and getter to get and set the variable name.

**Advantages**
1. Control Over Data : using getter or setter data.
2. Data Hiding  : using private data.
3. Easy To Test : using different classes.  
  
**For example**  
- consider a class called Car that has two data members: speed and fuel. We can encapsulate these data members by making them private and providing public methods to get and set their values, as shown below:

```
public class Car {
    private int speed;
    private int fuel;

    public int getSpeed() {
        return speed;
    }

    public void setSpeed(int speed) {
        this.speed = speed;
    }

    public int getFuel() {
        return fuel;
    }

    public void setFuel(int fuel) {
        this.fuel = fuel;
    }
}
```
**Here are some of the benefits of encapsulation:**
- It protects the data from being accessed or modified by unauthorized code.
- It improves the readability and maintainability of code.
- It helps to reduce the coupling between classes.
- It makes it easier to reuse code.
- It makes it easier to debug code.

## Inheritance
- Inheritance is a mechanism in Java that allows one object to acquire all the properties and behaviors of a parent object.
- This allows you to reuse code and makes your code more organized and maintainable.
- we used **extends** Keyword to achived Inheritance.

**Example**
```
class Vehicle {
  // code goes here
}

class Car extends Vehicle {
  // code goes here
}
```

- there are four types of Inheritance
  1. Single Inheritance.
  2. Multilevel Inheritance.
  3. Hierarchicle Inheritnce.
  4. Hybrid Inheritnce.
  5. Multiple Inheritnce.

### 1. Single Inheritance.
- Single inheritance is when a class (child class or subclass) inherits from one superclass (parent class).
- This means that the subclass can acquire the properties and methods of the superclass, enabling code reuse and the extension of existing functionality.
- Example :-
```
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
### 2. Multilevel Inheritance.
- Multilevel inheritance occurs when a class is derived from another derived class, forming a chain of classes. For example, class C inherits from class B, which inherits from class A.
- Example :- 
```
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
        puppy.eat();   // Inherited from Animal
        puppy.bark();  // Inherited from Dog
        puppy.play();  // Method of Puppy class
    }
}
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
        puppy.eat();   // Inherited from Animal
        puppy.bark();  // Inherited from Dog
        puppy.play();  // Method of Puppy class
    }
}
```
### 3. Hierarchical Inheritance.
- Hierarchical inheritance involves multiple classes inheriting from a single superclass. 
- This means one base class serves as the parent class for more than one child class.
- Example :- 
```
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
### 4. Multiple Inheritance
- Java does not support multiple inheritance directly through classes to avoid complexity and ambiguity (known as the "diamond problem").
- Instead, multiple inheritance is achieved using interfaces, where a class can implement multiple interfaces.
- Example :-
```
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
### 5. Hybrid Inheritance
- Hybrid inheritance is a combination of two or more types of inheritance.
- In Java, this typically involves a mix of single, multilevel, and multiple inheritance through interfaces.
- Example :-
```
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
## Super Keyword.
- the super keyword is used to refer to the superclass (parent class) of the current object.
- **Whenever you create the instance of subclass, an instance of parent class is created implicitly** which is referred by super reference variable.

### **Usage of Java super Keyword**

#### 1. Call a superclass constructor 
    - When a subclass needs to call a constructor from its superclass, super() is used.
    - Example :-
```
       class Animal {
    Animal() {
        System.out.println("Animal constructor called");
    }
}

class Dog extends Animal {
    Dog() {
        super(); // Calls the constructor of the superclass (Animal)
        System.out.println("Dog constructor called");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
    }
}
```
#### 2. Accessing a Superclass Method
  - Access a superclass method that has been overridden in the subclass.
  - If a method in the subclass overrides a method in the superclass, the super keyword can be used to call the overridden method from the superclass.
  - Example :- 
```
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
        super.eat(); // Calls the eat method of the superclass (Animal)
        eat();      // Calls the eat method of the current class (Dog)
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.display();
    }
}
```
#### 3.Accessing a Superclass Field
  - Access a superclass field that has been hidden by a field in the subclass
  - If a field in the subclass hides a field in the superclass, the super keyword can be used to access the hidden field.
   - Example :-
```
class Animal {
    String color = "white";
}

class Dog extends Animal {
    String color = "black";

    void display() {
        System.out.println("Dog color: " + color);         // Refers to the Dog class field
        System.out.println("Animal color: " + super.color); // Refers to the Animal class field
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.display();
    }
}

```

## Important Points to Remember:
Constructor Invocation: The super() call must be the first statement in the subclass constructor.
Method and Field Access: super can be used to access methods and fields from the immediate superclass only.
No super in static context: The super keyword cannot be used in a static context because it refers to the current instance of the subclass.
By using the super keyword, you can ensure that the subclass correctly initializes and interacts with its superclass, maintaining proper inheritance hierarchies and behaviors.









