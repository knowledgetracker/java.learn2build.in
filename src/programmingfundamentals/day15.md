---
title: Day 15 - Scanner
description: 
date: 2023-06-21
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
package day13;

import java.util.Scanner;

public class ScannerIntDemo {

	public static void main(String[] args) {

		Scanner scanner = new Scanner(System.in);
		System.out.println("Enter a your age: ");
		int name = scanner.nextInt();
		System.out.println("Your age is: " + name);
		scanner.close();

	}

}
```
- #####  Solved 2:
```java
package day13;

import java.util.Scanner;

public class ScannerDoubleDemo {

	public static void main(String[] args) {

		Scanner scanner = new Scanner(System.in);
		System.out.println("Enter a your age: ");
		Double name = scanner.nextDouble();
		System.out.println("Your age is: " + name);
		scanner.close();

	}

}
```
- ##### Solved 3:
```java
package day13;

import java.util.Scanner;


public class ScannerStringDemo {

	public static void main(String[] args) {

		Scanner scanner = new Scanner(System.in);
		System.out.println("Enter a your name: ");
		String name = scanner.nextLine();
		System.out.println("Your name is: " + name);
		scanner.close();
		
	}

}
```
- ##### Solved 4:
```java
package day13;

import java.util.InputMismatchException;
import java.util.Scanner;

public class ScannerExceptionHandlingDemo {

	public static void main(String[] args) {

		Scanner scanner = new Scanner(System.in);
		System.out.println("Enter a your age: ");
		
		try {

			int name = scanner.nextInt();
			System.out.println("Your age is: " + name);			
	
		} catch( InputMismatchException e) {

			System.out.println("Invalid age input");
			e.printStackTrace();

		}

		scanner.close();

	}

}
```
- ##### Solved 5:
```java
package day15;

import java.util.Scanner;

public class ScannerhasNextDemo {

	public static void main(String[] args) {
		// Create a string with multiple words
		String sentence = "Hello world! How are you?";

		// Create a scanner to read from the string
		Scanner scanner = new Scanner(sentence);

		
		while(scanner.hasNext()) {
			System.out.println(scanner.next());
		}

		// Check if the scanner has another token to read
		// Print the result
		System.out.println(scanner.hasNext());

		// Close the scanner
		scanner.close();
	}

}
```

### Practice
1. Write a Java program that prompts the user for their name and age and then prints a message saying "Hello, [name]. Next year, you'll be [age+1]".
2. Write a Java program that takes a string as input and counts the number of vowels in it.
3. Write a Java program that accepts a string from the user and removes all duplicate characters from it.
4. Write a Java program that reads a sentence from the user and then rearranges the words in reverse order

