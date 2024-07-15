# Methods
- A method in Java is a block of code that performs a specific task.
- Methods are used to define the behavior of objects in a class.
- A method can take input parameters and return a value, but it is not necessary.
  
**Use Of Method :**  
- The primary uses of methods in Java are: It allows code reusability (define once and use multiple times).  
- You can break a complex program into smaller chunks of code.  
- It increases code readability.

**How to Used Methode**
- A method typically consists of three parts:
    1. Declaration: Specifies the method's name, return type, and parameters (if any).  
    2. Definition: Contains the actual implementation or body of the method.  
    3. Calling of method: Invoking or using the method in your code.  

**Syntax Of Method**
  ```
    access-modifier return-type method-name(parameter-list) {
      // method body
    }
  ```
**Example Of method**
```
  public int addNumbers(int a, int b) {
    return a + b;
  }
```
## Here's a revised some points about methods 

- Methods are used to encapsulate a logical block of code.

- A method typically consists of three parts:
    1. Declaration: Specifies the method's name, return type, and parameters (if any).
    2. Definition: Contains the actual implementation or body of the method.
    3. Calling of method: Invoking or using the method in your code.

- A method in programming languages generally returns a value or nothing (void).

- The return type declared and defined for a method should match. For example, if you declare a method to return an integer (int), its definition should end with a return statement that returns an int.

- In a void-typed method, data is printed rather than returned. This means the method performs actions (like printing to the console) but does not return a value.

- Parameters are passed in the method declaration and are always of a specific data type, though they are optional depending on the method's design.

- Arguments are values passed to a method when calling it. These values correspond to the parameters defined in the method declaration.








package Methods;

public class Methods_practice {

    static void swapTwoNum(int firstNumber, int secondNumber) {
        int temp = firstNumber;
        firstNumber = secondNumber;
        secondNumber = temp;
        System.out.println(firstNumber + " " + secondNumber);
    }

    static int greatestOfThree(int firstNumber, int secondNumber, int thirdNumber) {
        int ans;
        if (firstNumber > secondNumber && firstNumber > thirdNumber) {
            ans = firstNumber;
        } else if (secondNumber > firstNumber && secondNumber > thirdNumber) {
            ans = secondNumber;
        } else {
            ans = thirdNumber;
        }
        return ans;
    }

    static boolean userSalary(int salary) {
        if (salary >= 20000 && salary <= 40000) {
            return true;
        } else {
            return false;
        }
    }


    public static void main(String[] args) {

        swapTwoNum(5, 6);

        int greatestNumber = greatestOfThree(1, 2, 3);
        System.out.println("Greatest of three  " + greatestNumber);

        System.out.println(userSalary(40000));

    }
}




