---
title: Day 06 - String Utilities
description: 
date: 2023-06-08
duration: 3 hrs
solved: 0
practice: 0
hots: 0
tags:
  - java
layout: layouts/post.njk
---


### Solved
- #####  Solved 1:

```java
package day06;

public class StringDemo {

	public static void main(String[] args) {
	
        //input
        String firstName = "Surya" ;
        String lastName = "Umapathy";
         
        //business logic
        String fullName = firstName + " " + lastName;     
         
        //output
        System.out.println(fullName);
		
		
	}

}
```
- ##### Solved 2: 
```java
package day06;

public class StringConcatDemo {

	public static void main(String[] args) {
	
        //input
        String firstName = "Surya" ;
        String lastName = "Umapathy";
         
        //business logic
        String fullName = firstName.concat(lastName);     
         
        //output
        System.out.println(fullName);
		
	}

}

```


- ##### Solved 3: 
``` java
package day06;

public class StringTrimDemo {

	public static void main(String[] args) {

		// input
		String firstName = "    Surya     ";

		// output
		System.out.println("Without Trim method: " + firstName);		
		System.out.println("With Trim method: " + firstName.trim());

		System.out.println("length Without Trim method: " + firstName.length());
		System.out.println("Length With Trim method: " + firstName.trim().length());
		
	}

}
```

- ##### Solved 4: 
```java
package day06;

public class StringCompareDemo {

	public static void main(String[] args) {

		// input
		String name1 = "    Surya     ";
		String name2 = "Surya";

		// output
		System.out.println("Comparing without .trim()");
		System.out.println("Comparing using comparsion operator (==): " + (name1 == name2));
		System.out.println("Comparing using .equals() method: " + name1.equals(name2)); // Best practice

		System.out.println("\nComparing with .trim()");
		System.out.println(name1.trim() == name2.trim());
		System.out.println(name1.trim().equals(name2.trim()));
	}

}
```

- ##### Solved 5: 
```java

/**
 * @author SuryaUmapathy
 *
 */

// User.java
public class User {
    String firstName;
    String lastName;
    String email;
    String password;
    String phoneNumber;

    public User(String firstName, String lastName, String email, String password, String phoneNumber) {
        
				// trim and convert names to title case
        this.firstName = firstName.trim().substring(0, 1).toUpperCase() + firstName.substring(1).toLowerCase();
        this.lastName = lastName.trim().substring(0, 1).toUpperCase() + lastName.substring(1).toLowerCase();
        
        // trim and convert email to lowercase
        this.email = email.trim().toLowerCase();
        
        // password is saved as is
        this.password = password;
        
        // trim phone number
        this.phoneNumber = phoneNumber.trim();
    }

    public String getFullName() {
        // concat first and last names
        return this.firstName.concat(" ").concat(this.lastName);
    }

    public boolean authenticate(String passwordToCheck) {
        // check if provided password matches the stored one
        return this.password.equals(passwordToCheck);
    }

    @Override
    public String toString() {
        String userDetails = "Name: " + getFullName() + ", Email: " + email + ", Phone Number: " + phoneNumber;
        System.out.println(userDetails);
        return userDetails;
    }
}


// App.java
public class App {
    public static void main(String[] args) {
        User newUser = new User("john", "doe", " jDoe@EXAMPLE.Com ", "password123", " 123-456-7890 ");
        newUser.toString();

        // checking password
        System.out.println(newUser.authenticate("password123"));  // prints: true
        System.out.println(newUser.authenticate("wrongpassword"));  // prints: false
    }
}
```

- ##### Solved 6:
``` java
package com.fssa.learnJava.fop.day06;

/**
 * In this example, we start with the originalString variable containing the
 * value "Hello". Then, we use the concat() method to concatenate " World!" to
 * the original string and store the result in the modifiedString variable.
 * However, notice that the original string remains unchanged.
 * 
 * This behaviour demonstrates the immutability of the String class. When you
 * perform any operation on a String object, such as concatenation, the original
 * string remains unaltered, and a new String object is created with the
 * modified value. This immutability property ensures that strings are safe to
 * share across different parts of a program without worrying about their
 * content being changed unexpectedly.
 * 
 * @author BharathwajSoundarara
 *
 */
public class StringImmutabilityDemo {
	public static void main(String[] args) {
		// Declaring a string
		String originalString = "Hello";
		System.out.println("Original String: " + originalString);

		// Concatenating another String to the Original String
		String modifiedString = originalString.concat(" World!");

		// ModifiedString after concatenation
		System.out.println("Modified String: " + modifiedString);

		// Unchanged Original String
		System.out.println("Original String after modification: " + originalString);
	}
}
```

### Practice

```
1. Write a Java program that takes your firstname and lastname and concatenates them into your fullname.
2. Write a Java program that takes a predefined string "John Doe", and prints the full name in uppercase.
3. Write a Java program that takes a predefined sentence "Hello, World!", then prints the length of the sentence and the first character.
4. Write a Java program that takes a predefined string "Jane Doe", then prints the first name and last name separately (assume the first name and last name are separated by a space).
5. Write a Java program that takes a predefined string "surya umapathy", and capitalizes the first letter of the first and last names to output "Surya Umapathy". Assume the first name and last name are separated by a space.

```java
//  convert the String 
//  "surya umapathy"  ===>  "Surya Umapathy"
//  "john doe"        ===> "John Doe"
```

```


