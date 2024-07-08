# Strings in Java

## Overview
A `String` variable contains a collection of characters surrounded by double quotes. Strings in Java are immutable, meaning once a `String` object is created, it cannot be changed.

## Ways of Creating Strings

1. **String Literal**
    - Strings created using string literals are stored in a common pool and reused if they already exist.

    ```java
    String name = "Ashpak";  // Stored in static memory (string pool)
    ```

2. **Using `new` Keyword**
    - Strings created using the `new` keyword are stored in the heap memory.

    ```java
    String newName = new String("Ashpak");  // Stored in heap memory
    ```

## String Methods and Operations

### Concatenation
Combining two strings using the `+` operator or the `concat()` method.

```java
String firstName = "NITIN";
String lastName = "Patel";
System.out.println(firstName + lastName);         // NITINPatel
System.out.println(firstName.concat(lastName));   // NITINPatel
```

### Length()
- Getting the length of the string.
```
System.out.println(firstName.length());  // 5
```
### charAt()
Extracting a character from a string at a specified index.
```
System.out.println(lastName.charAt(3));  // e
```
### substring()
Extracting a substring from a string.
```
System.out.println(firstName.substring(1, 3));  // IT
```
### equals()
Checking if two strings are equal.
```
System.out.println(firstName.equals(lastName));  // false
```
### contains()
Checking if a string contains a specified sequence of characters.
```
System.out.println(firstName.contains("As"));  // false
```
### indexOf()
Finding the index of a character in a string.
```
System.out.println(firstName.indexOf('s'));  // -1 (character not found)
```
### replace()
Replacing characters in a string.
```
System.out.println(firstName.replace('N', 'n'));  // NITIN ('N' replace to 'n')
```
### split()
Splitting a string into an array of substrings.
```
String[] ans = firstName.split("T");
System.out.println(ans[0]);  // NI
System.out.println(ans[0]);  // IN
```
### Example Program : Reversing a String and Checking for Palindrome
```
package DSA;

public class Strings {
    public static void main(String[] args) {
        String firstName = "NITIN";
        String reversName = "";
        
        for(int i = firstName.length()-1; i >= 0 ; i--){
            reversName += firstName.charAt(i);
        }
        System.out.println("Reversed String = " + reversName);

        if(firstName.equals(reversName)){
            System.out.println("Is palindrome: " + true);
        } else {
            System.out.println("Is palindrome: " + false);
        }
    }
}
```
### Explanation
- The program initializes a String variable firstName with the value "NITIN".
- It then reverses the string and checks if the reversed string is equal to the original string.
- If they are equal, the string is a palindrome.
