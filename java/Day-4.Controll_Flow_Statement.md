# Java Control Statements | Control Flow in Java

The Java compiler executes the code from top to bottom. Java provides statements that can be used to control the flow of Java code. Such statements are called control flow statements.

1. **Decision Making Statements**
   - if statements
   - switch statement
2. **Loop Statements**
   - do while loop
   - while loop
   - for loop
   - for-each loop
3. **Jump Statements**
   - break statement
   - continue statement

## If Statement
- Enables the program to enter a block of code if the expression evaluates to true.
- Example:
    ```java
    public class Main {
        public static void main(String[] args) {
            int x = 10;
            int y = 12;
            if(x + y > 20) {
                System.out.println("x + y is greater than 20");
            }
        }
    }
    ```

## If-Else Statement
- The if-else statement is an extension to the if-statement, which uses another block of code, i.e., else block. The else block is executed if the condition of the if-block is evaluated as false.
- Example:
    ```java
    public class Student {
        public static void main(String[] args) {
            int x = 10;
            int y = 12;
            if(x + y < 10) {
                System.out.println("x + y is less than 10");
            } else {
                System.out.println("x + y is greater than 20");
            }
        }
    }
    ```

## If-Else-If Ladder
- The if-else-if statement contains the if-statement followed by multiple else-if statements.
- Example:
    ```java
    public class Student {
        public static void main(String[] args) {
            String city = "Delhi";
            if(city.equals("Meerut")) {
                System.out.println("City is Meerut");
            } else if (city.equals("Noida")) {
                System.out.println("City is Noida");
            } else if(city.equals("Agra")) {
                System.out.println("City is Agra");
            } else {
                System.out.println(city);
            }
        }
    }
    ```

## Nested If-Statement
- In nested if-statements, the if statement can contain an if or if-else statement inside another if or else-if statement.
- Example:
    ```java
    public class Student {
        public static void main(String[] args) {
            String address = "Delhi, India";

            if(address.endsWith("India")) {
                if(address.contains("Meerut")) {
                    System.out.println("Your city is Meerut");
                } else if(address.contains("Noida")) {
                    System.out.println("Your city is Noida");
                } else {
                    System.out.println(address.split(",")[0]);
                }
            } else {
                System.out.println("You are not living in India");
            }
        }
    }
    ```

## Switch Case  
- The switch statement in Java is a control flow statement that allows you to execute different blocks of code based on the value of a variable. It is similar to the if-else statement, but it can be used to handle multiple cases more easily.
- The expression in the switch statement is evaluated, and the corresponding case block is executed. If no case matches the value of the expression, the default block is executed.
    ```java
   switch (expression) {
  case value1:
    // code block
    break;
  case value2:
    // code block
    break;
  default:
    // code block
   }
    ```
