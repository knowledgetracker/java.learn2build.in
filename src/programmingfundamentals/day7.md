---
title: Day 07 - Conditional Statements
description: 
date: 2023-06-09
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
package day07;

public class ConditionalStatementDemo {

	public static void main(String[] args) {
		
	    int marks = 85;
    
      if ( marks >= 75 ) {
          System.out.println("You got an A grade");
      }
      
	}

}
```
- ##### Solved 2: 
```java
package day07;

public class ConditionalStatementDemo2 {

	public static void main(String[] args) {

		int mark = 65;

		if (mark >= 75) {
			System.out.println("You got an A grade");
		} else {
			System.out.println("You didn't get an A grade");
		}

	}

}

```


- ##### Solved 3: 
``` java
package day07;

public class ConditionalStatementDemo3 {

	public static void main(String[] args) {

		int mark = 70;

		if (mark >= 75) {
			System.out.println("You got an A grade");
		} else if(mark >= 60) { 
			System.out.println("You got an B grade");
		} else if(mark >= 45) { 
			System.out.println("You got an C grade");
		} else {
			System.out.println("You didn't get an A, B or C grade");
		}

	}

}
```

- ##### Solved 4: 
```java
package day07;

public class ConditionalStatementDemo4 {

	public static void main(String[] args) {

		int day = 4;

		switch (day) {
		case 1:
			System.out.println("Today is Monday");
			break;
		case 2:
			System.out.println("Today is Tuesday");
			break;
		case 3:
			System.out.println("Today is Wednesday");
			break;
		case 4:
			System.out.println("Today is Thursday");
			break;
		case 5:
			System.out.println("Today is Friday");
			break;
		case 6:
			System.out.println("Today is Saturday");
			break;
		case 7:
			System.out.println("Today is Sunday");
			break;
		default:
			System.out.println("Invalid day");
			break;
		}

	}

}
```



### Practice

```
1. Write a Java program that reads an integer. If the number is positive, print "The number is positive." If the number is negative, print "The number is negative." If the number is zero, print "The number is zero."
2. Write a Java program that reads a character. If the character is a vowel, print "The character is a vowel." If the character is a consonant, print "The character is a consonant." Make sure to handle both upper and lower case letters.
```


