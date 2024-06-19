
## 1. You're creating a program to evaluate job applicants based on their qualifications and experience. Implement a Java program using if-else statements to assess the eligibility of each applicant for a job position.

```java
import java.util.Scanner;

public class ApplicantEvaluation {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("What is your qualification");
        System.out.println("Enter 1 for 10th");
        System.out.println("Enter 2 for 12th");
        System.out.println("Enter 3 for graduation");

        int qualification = sc.nextInt();

        System.out.println("Enter how many years of experience you have");

        int experience = sc.nextInt();

        if (qualification == 3 && experience > 2) {
            System.out.println("You are eligible for the interview");
        } else {
            System.out.println("You are not eligible");
        }
    }
}
```

## 2. You're developing a program to calculate the final grade of a student based on their test scores. Implement a Java program using if-else statements to determine the grade according to the following grading scale:
- If the score is between 90 and 100 (inclusive), assign grade A.
- If the score is between 80 and 89 (inclusive), assign grade B.
- If the score is between 70 and 79 (inclusive), assign grade C.
- If the score is between 60 and 69 (inclusive), assign grade D.
- If the score is below 60, assign grade F.

```java
import java.util.Scanner;

public class GradeCalculation {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter your test score:");

        int testScore = sc.nextInt();

        if (testScore >= 90 && testScore <= 100) {
            System.out.println("Your grade is A");
        } else if (testScore >= 80 && testScore <= 89) {
            System.out.println("Your grade is B");
        } else if (testScore >= 70 && testScore <= 79) {
            System.out.println("Your grade is C");
        } else if (testScore >= 60 && testScore <= 69) {
            System.out.println("Your grade is D");
        } else {
            System.out.println("FAIL");
        }
    }
}

```
## 3. Weather Recommendation Program
Implement a Java program using if-else statements to provide activity recommendations based on the current temperature:
- If the temperature is below 10°C, recommend skiing.
- If the temperature is between 10°C and 20°C (inclusive), recommend hiking.
- If the temperature is between 20°C and 30°C (inclusive), recommend cycling.
- If the temperature is above 30°C, recommend swimming.

```java
import java.util.Scanner;

public class WeatherRecommendation {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter the current temperature in °C:");

        int temperature = sc.nextInt();

        if (temperature < 10) {
            System.out.println("We recommend skiing.");
        } else if (temperature >= 10 && temperature <= 20) {
            System.out.println("We recommend hiking.");
        } else if (temperature >= 20 && temperature <= 30) {
            System.out.println("We recommend cycling.");
        } else {
            System.out.println("We recommend swimming.");
        }
    }
}
```

## 4. Restaurant Bill Calculation Program

Implement a Java program using if-else statements to calculate the bill based on the items ordered and their prices, and apply any applicable discounts or service charges:
- Starter: $5.00
- Main Course: $10.00
- Dessert: $4.50
- Drinks: $2.50

Additional rules:
- If the total bill is above $50, apply a 10% discount.
- If the customer orders a dessert, offer a 20% discount on the dessert if they also order a main course.

```java
import java.util.Scanner;

public class RestaurantBill {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        double starterPrice = 5.00;
        double mainCoursePrice = 10.00;
        double dessertPrice = 4.50;
        double drinksPrice = 2.50;

        System.out.println("Enter the number of starters ordered:");
        int starterCount = sc.nextInt();

        System.out.println("Enter the number of main courses ordered:");
        int mainCourseCount = sc.nextInt();

        System.out.println("Enter the number of desserts ordered:");
        int dessertCount = sc.nextInt();

        System.out.println("Enter the number of drinks ordered:");
        int drinksCount = sc.nextInt();

        double totalBill = (starterCount * starterPrice) + (mainCourseCount * mainCoursePrice)
                            + (dessertCount * dessertPrice) + (drinksCount * drinksPrice);

        if (dessertCount > 0 && mainCourseCount > 0) {
            totalBill -= dessertCount * dessertPrice * 0.20;  // 20% discount on desserts
        }

        if (totalBill > 50) {
            totalBill *= 0.90;  // 10% discount on total bill
        }

        System.out.println("Your total bill is: $" + totalBill);
    }
}
```

## Library Fine Calculation Program

Implement a Java program using if-else statements to determine the fine based on the number of days the book is overdue:
- If the book is returned within 7 days of the due date, there is no fine.
- If the book is returned between 8 and 30 days after the due date, the fine is $1.00 per day.
- If the book is returned more than 30 days after the due date, the fine is $2.00 per day.


```java
import java.util.Scanner;

public class LibraryFine {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter the number of days the book is overdue:");
        int daysOverdue = sc.nextInt();

        double fine;

        if (daysOverdue <= 7) {
            fine = 0.00;
        } else if (daysOverdue <= 30) {
            fine = 1.00 * (daysOverdue - 7);
        } else {
            fine = (1.00 * 23) + (2.00 * (daysOverdue - 30));
        }

        System.out.println("The total fine is: $" + fine);
    }
} ```
