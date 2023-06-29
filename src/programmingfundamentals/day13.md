---
title: Day 13 - Validation (Part 2)
description: 
date: 2023-06-19
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

package day11;

public class NumberValidationDemo {

	public static void main(String[] args) {

		int input = 6;

		if (input >=1 && input <= 10) {
			System.out.println("The number is within the range [1, 10]");
		} else {
			System.out.println("The number is outside the range [1, 10]");
		}

	}

}
```
- ##### Solved 2: 
```java
package day11;

public class StringValidationDemo {

	public static void main(String[] args) {

		String input = "Surya";

		if (input == null) {
			System.out.println("The input String is Null");
		} else if (input.trim().isEmpty()) {
			System.out.println("The input String is Empty");
		} else {
			System.out.println("The Input String is: " + input);
		}

	}

}
```

- ##### Solved 3:
```java
package day11;

import java.util.regex.Pattern;

public class EmailValidationDemo {

	public static void main(String[] args) {

		String email = "surya.umapathy@freshworks.com";
		String regex = "^.*@.*\\..*$";

		Boolean isMatch = Pattern.matches(regex, email);

		if (isMatch) {
			System.out.println("The email address is: Valid");
		} else {
			System.out.println("The email address is: Invalid");
		}

	}

}
```
- ##### Solved 4:
```java
import java.util.Scanner;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * Demonstrate Simple RegEx and also create simple RegExs
 * Its a Playground
 * @author BharathwajSoundarara
 *
 */
public class RegexPlayground {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		String exitCode = "Continue";
		
		while (!"exit".equalsIgnoreCase(exitCode)) {
			// Reading the RegEx from the user
			System.out.println("Enter the regex: ");
			String regEx = sc.nextLine();
			Pattern pattern = Pattern.compile(regEx);
			
			// Reading the string to search using the RegEx
			System.out.println("Enter input string to search: ");
			String inputString = sc.nextLine();
			
			// Match the String Entered by the user
			// With the RegEx they had shared
			Matcher matcher = pattern.matcher(inputString);

			boolean found = false;
			
			while (matcher.find()) {
				System.out.printf("I found the text" + " \"%s\" starting at " + "index %d and ending at index %d.%n",
						matcher.group(), matcher.start(), matcher.end());
				found = true;
			}
			if (!found) {
				System.out.format("No match found.%n");
			}
			System.out.println("Type exit to exit code or continue: ");
			exitCode = sc.nextLine();
		}
		sc.close();
	}
}
```

### Practice

```
1. Write a Java method to validate a phone number. A valid phone number consists of 10 digits.
2. Write a Java method to validate an email address. A valid email address should contain '@' and '.' characters.
3. Write a Java method to validate a string length. The string should be minimum 5 characters and maximum 15 characters.
4. Write a Java method to validate a password. A valid password should contain at least one uppercase letter, one lowercase letter, one digit, and one special character, and it should be at least 8 characters long.
5. Create a separate class `UserValidator` and a method `UserValidator.validate(User user)` that validate each of the attributes of the below class. Please add the validation of id should be Positive, name should be of minimum length 2,  use the Practice#4 rules for validating password, use Practice#2 to validate email. Use the below User class

```java
public class User {
	int id;
	String name;
	String password;
	String email;
	
	public int getId() {
		return id;
	}
	public void setId(int id) {
		this.id = id;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public String getPassword() {
		return password;
	}
	public void setPassword(String password) {
		this.password = password;
	}
	public String getEmail() {
		return email;
	}
	public void setEmail(String email) {
		this.email = email;
	}
	
	
}
```


