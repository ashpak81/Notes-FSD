## Strings in Java

### Overview
A `String` in Java represents a sequence of characters and is a fundamental data type. Strings are immutable, meaning that once a `String` object is created, it cannot be altered. Any modification to a `String` results in the creation of a new `String` object.

### Ways of Creating Strings

1. **String Literal**
   - Strings created using string literals are stored in a common pool, which allows for reuse of identical strings.
   
   ```java
   String name = "Ashpak";  // Stored in string pool
   ```

2. **Using `new` Keyword**
   - Strings created with the `new` keyword are allocated in heap memory, bypassing the string pool.
   
   ```java
   String newName = new String("Ashpak");  // Stored in heap memory
   ```

### String Methods and Operations

**1. Concatenation**
   - Combine two strings using the `+` operator or `concat()` method.
   
   ```java
   String firstName = "NITIN";
   String lastName = "Patel";
   System.out.println(firstName + lastName);         // NITINPatel
   System.out.println(firstName.concat(lastName));   // NITINPatel
   ```

**2. `length()`**
   - Returns the number of characters in the string.
   
   ```java
   System.out.println(firstName.length());  // 5
   ```

**3. `charAt(int index)`**
   - Retrieves the character at the specified index.
   
   ```java
   System.out.println(lastName.charAt(3));  // e
   ```

**4. `substring(int beginIndex, int endIndex)`**
   - Extracts a portion of the string between specified indices.
   
   ```java
   System.out.println(firstName.substring(1, 3));  // IT
   ```

**5. `equals(Object obj)`**
   - Compares the string with another string for equality.
   
   ```java
   System.out.println(firstName.equals(lastName));  // false
   ```

**6. `contains(CharSequence sequence)`**
   - Checks if the string contains the specified sequence of characters.
   
   ```java
   System.out.println(firstName.contains("As"));  // false
   ```

**7. `indexOf(int ch)`**
   - Returns the index of the first occurrence of the specified character.
   
   ```java
   System.out.println(firstName.indexOf('s'));  // -1 (character not found)
   ```

**8. `replace(CharSequence target, CharSequence replacement)`**
   - Replaces all occurrences of a specified character or substring with another.
   
   ```java
   System.out.println(firstName.replace('N', 'n'));  // nITIN
   ```

**9. `split(String regex)`**
   - Splits the string into an array of substrings based on the specified regular expression.
   
   ```java
   String[] ans = firstName.split("T");
   System.out.println(ans[0]);  // NI
   System.out.println(ans[1]);  // IN
   ```

### Example Program: Reversing a String and Checking for Palindrome

Here’s a simple Java program to reverse a string and check if it’s a palindrome:

```java
package DSA;

public class Strings {
    public static void main(String[] args) {
        String firstName = "NITIN";
        String reversedName = "";
        
        // Reversing the string
        for(int i = firstName.length() - 1; i >= 0; i--){
            reversedName += firstName.charAt(i);
        }
        System.out.println("Reversed String = " + reversedName);

        // Checking for palindrome
        if(firstName.equals(reversedName)){
            System.out.println("Is palindrome: true");
        } else {
            System.out.println("Is palindrome: false");
        }
    }
}
```

**Explanation:**
- **String Initialization:** The `firstName` variable is initialized with the value `"NITIN"`.
- **Reversing the String:** The `for` loop iterates through the string from end to start, appending each character to `reversedName`.
- **Palindrome Check:** Compares the original string `firstName` with `reversedName`. If they are equal, the string is a palindrome.
