## Swap two Numbers
```
public class Student {    
public static void main(String[] args) {  
  int firstNumber = 12;
  int secondNumber = 13;
System.out.println("Before execution value of a is "+ a + "and b is "+ b);
  int temp;
  temp = firstNumber;
  firstNumber = secondNumber;
  secondNumber = temp;
System.out.println("After execution value of a is "+ a + "and b is "+ b)
}
}
```
## Swap Number without using third veriable
```
public class Student {    
public static void main(String[] args) {  
  int firstNumber = 12;
  int secondNumber = 13;
System.out.println("Before execution value of a is "+ a + "and b is "+ b);
  firstNumber = firstNumber + secondNumber;
  secondNumber = firstNumber - secondNumber;
  firstNumber = firstNumber - secondNumber;
System.out.println("After execution value of a is "+ a + "and b is "+ b)
}
}
```

## Voter Program 
```
public class voter{
public static void main(String[] args){
      Scanner sc = new Scanner(System.in);
        System.out.println("Enter your age : ");
        int age = sc.nextInt();
        System.out.println("do you have citizenship ? if yes enter 'true' else enter false");
        boolean Indian = sc.nextBoolean();
        System.out.println("do you have voter if ? if yes enter 'true' else enter false ");
        boolean Voter = sc.nextBoolean();

        if (age >= 18) {
            if (Indian == true) {
                if (Voter == true) {
                    System.out.println("You can vote now");
                } else {
                    System.out.println("You dont have voter card , you cant vote");
                }
            } else {
                System.out.println("you are not Indian ,you cant vote");
            }
        } else {
            System.out.println("your age is less than 18 , you cant vote");
        }
  }
}
```
##  User Id and password login System

```
public class student{
public static void main(String[] args){
    Scanner sc = new Scanner(System.in);
     System.out.println("Enter user Id ");
        int user_id = sc.nextInt();
        System.out.println("Enter password ");
        int pass = sc.nextInt();

        if (user_id == 123) {
            if (pass == 321) {
                System.out.println("You are Login !!");
            } else {
                System.out.println("Password is Wrong");
            }
        } else {
            System.out.println("User id is Wrong");
        }
  }
}
```
