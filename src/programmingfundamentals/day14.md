---
title: Day 14 - Utilities
description: 
date: 2023-06-20
duration: 3 hrs
solved: 0
practice: 0
hots: 0
tags:
  - java
layout: layouts/post.njk
---

#### Date, LocalDate & LocalDateTime
### Solved
- #####  Solved 1:

```java

package day12;

import java.time.LocalDate;
import java.time.LocalDateTime;
import java.util.Date;

public class DateDemo {

	public static void main(String[] args) {
		
		Date date = new Date();
		System.out.println(date);		
		
		LocalDate today = LocalDate.now();
	  System.out.println(today);
	  
	  LocalDateTime now = LocalDateTime.now();
	  System.out.println(now);

	}

}
```
- ##### Solved 2: 
```java
package day12;

import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class DateDemo2 {

	public static void main(String[] args) {

		// today's Date
		LocalDate today = LocalDate.now();

		// Expected format
		DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yy");

		// Converting date to the format
		String formattedDate = today.format(formatter);
		System.out.println(formattedDate);
	}

}
```

- ##### Solved 3:
```java
package day12;

import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class DateDemo3 {

	public static void main(String[] args) {

		// Date in String format
		String dateString = "2023-05-21";

		// Format the DateString is In.
		DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd");

		// Converting dateString to LocalDate
		LocalDate parsedDate = LocalDate.parse(dateString, formatter);
		System.out.println(parsedDate);
		System.out.println(parsedDate.getYear());
		System.out.println(parsedDate.getMonth());
		System.out.println(parsedDate.getMonthValue());
		System.out.println(parsedDate.getDayOfMonth());
		
	}

}
```
- ##### Solved 4:
 ```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class DateDemo4 {

	public static void main(String[] args) {

		String dateStr = "2023/05/21"; 
		// Expected in "yyyy-MM-dd" format, but it's in "yyyy/MM/dd" format.
		
		DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy/MM/dd");

		try {

			LocalDate parsedDate = LocalDate.parse(dateStr, formatter);
			System.out.println(parsedDate);

		} catch (Exception e) {

			System.out.println("Failed to parse the date: " + e.getMessage());
			e.printStackTrace();

		}

	}

}
```
Additional Solved: Tatkal Train Ticket – Date validation using LocalDate methods
```java
/**
 * 
 */
package day14.solved;

import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class DateDemo5 {

	public static void main(String[] args) throws Exception {
		LocalDate currentDate = LocalDate.now();
		LocalDate journeyDate = LocalDate.parse("2023-06-14");

		System.out.println("Todays Date :" + currentDate + ", Journey Date:" + journeyDate);
		if (journeyDate.isBefore(currentDate)) {
			throw new Exception("Journey Date cannot be less than current date");
		}
		LocalDate tatkalDate = currentDate.plusDays(1);
		System.out.println("Note:Tatkal ticket can be booked on or before :" + tatkalDate);
		if (tatkalDate.isBefore(journeyDate)) {
			System.out.println("Tatkal ticket cannot be booked:" + journeyDate);
		} else {
			System.out.println("Tatkal Ticket booked for :" + journeyDate);
		}
	}
}
```
 ##### StringBuffer & StringBuilder
 - ##### Solved 1:
```java
package day12;

public class StringBuilderDemo {

	public static void main(String[] args) {

		String firstName = "Surya";
		String lastName = "Umapathy";

		StringBuilder fullName = new StringBuilder();
		fullName.append(firstName);
		fullName.append(" ");
		fullName.append(lastName);

		System.out.println(fullName);

	}

}
```
 - ##### Solved 2:
```java
package day12;

public class StringBufferDemo {

	public static void main(String[] args) {
    
      String firstName = "Surya";
      String lastName = "Umapathy";
      
      StringBuffer fullName = new StringBuffer();
      fullName.append(firstName).append(" ").append(lastName);
      
      System.out.println(fullName);
	
	}

}
```
 - ##### Solved 3: Insert a string at a specific position in a **StringBuilder** using the **insert()** method
 ```java
 public class StringBuilderInsert {
    public static void main(String[] args) {
        StringBuilder builder = new StringBuilder("Hello World");
        builder.insert(5, "Beautiful ");
        System.out.println(builder.toString());
    }
}
```
 - ##### Solved 4:Reverse a string using **reverse()** method in **StringBuilder**
```java
public class StringBuilderReverse {
    public static void main(String[] args) {
        StringBuilder builder = new StringBuilder("Hello");
        builder.reverse();
        System.out.println(builder.toString());
    }
}
```

 - ##### Solved 5:Appending Array of Strings to create a Single string.
 ```java
 /**
 * Class created for demonstrating appending with String builder
 * 
 * @author BharathwajSoundarara
 *
 */
public class StringBuilderLoopAppender {
	public static void main(String[] args) {

		// Program to demonstrate creating a String
		// Appending a array of Strings
		String[] strArr = { "This", "is", "a", "collection", "of", "words", "to",
				"be", "appended", "to", "form", "a", "Sentence" };
		
		// Without String Builder
		String newStrFromSent = "";
		for (String str: strArr ) {
			// We are creating a new String everytime we do this
			newStrFromSent +=  str + " ";
		}
		System.out.println(newStrFromSent.trim());
		
		// GOOD Practice: With String Builder 
		
		StringBuilder strBuilderFromSent = new StringBuilder();
		
		for (String str: strArr) {
			// Just appending to an already existing object
			strBuilderFromSent.append(str);
			strBuilderFromSent.append(" ");
		}
		System.out.println(strBuilderFromSent.toString().trim());
	}
}
```




### Practice


1. Import the Calculator package from `day04` and use it to add two integers. 
2. Write a Java program to display the current date and time using the **`LocalDateTime`** class.
3. Write a Java program to create a **`LocalDate`** object representing your birthday.
4. Write a Java program to calculate the number of days between two **`LocalDate`** objects.
5. Write a Java program that uses the **`Date`** class to print the current date and time in the following format: "Today's date is MM/DD/YYYY and current time is HH:MM:SS".
6. Write a program that takes a sentence as input from the user and reverses the order of the words in the sentence. The program should use **`StringBuilder`** to perform the reversal.
    
    Example:
    Input: "Hello, how are you?"
    Output: "you? are how Hello,"
    
7. **Insert a string** at a specific position in a `StringBuilder` using the `insert()` method



