---
title: Day 10 - Exception Handling ((Part 1)
description: 
date: 2023-06-14
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
/**
 * Demo for Integer parsing and number format exception
 * @author BharathwajSoundarara
 *
 */
public class NumberFormatExceptionDemo {
	public static void main(String[] args) {
		try {
			String ageStr = "Twenty";
			int age = Integer.parseInt(ageStr);// Throws an NFE exception
			System.out.println("Age convered" + age);
		} catch (NumberFormatException e) {
			System.out.println(e.getMessage());
			e.printStackTrace();
		}

	}
}
```

- ##### Solved 2: 
```java
package day10;

public class ExceptionHandlingDemo {

	public static void main(String[] args) {
		
		String name = null;
		
		try {
			
			int length = name.lengthgt ();
			System.out.println(length);
			
		} catch (Exception e) {

			System.out.println(e.getMessage());
			e.printStackTrace();
			
		}

	}

}

```


- ##### Solved 3: 
``` java
/**
 * Demo of what happens when we access more elements
 * 
 * @author BharathwajSoundarara
 *
 */
public class ArrayOutOfBoundsDemo {
	public static void main(String[] args) {
		int[] intArr = { 49, 50, 70 };

		// Trying access an element which is not initialised and declared
		intArr[4] = 80;
	}
}
```

Output:

```java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 4 out of bounds for length 3
	at com.fssa.learnJava.fop.day10andday11.ArrayOutOfBoundsDemo.main(ArrayOutOfBoundsDemo.java:14)
  ```

- ##### Solved 4:
```java
/**
 * Handling the ArrayIndexOutOfBoundsException with a try catch
 * 
 * @author BharathwajSoundarara
 *
 */
public class ArrayOutOfBoundsWithException {
	public static void main(String[] args) {
		try {
			int[] intArr = { 49, 50, 70 };

			// Trying access an element which is not initialised and declared
			intArr[4] = 80;
		} catch (ArrayIndexOutOfBoundsException e) {
			System.out.println(e.getMessage());
			e.printStackTrace();
		}
	}
}
```

Output:
```java
Index 4 out of bounds for length 3
java.lang.ArrayIndexOutOfBoundsException: Index 4 out of bounds for length 3
	at com.fssa.learnJava.fop.day10andday11.ArrayOutOfBoundsWithException.main(ArrayOutOfBoundsWithException.java:15)
```

- ##### Solved 5: Checked Exception example
``` java
**
 * 
 */
package day11;

import java.io.FileNotFoundException;
import java.io.FileReader;

/**
 * @author VinitGore
 *
 */
public class CompileTimeExceptionDemo {

	public static void main(String[] args) {
		// try {
			FileReader fileReader = new FileReader("example.txt"); // This line may throw a FileNotFoundException
		// } catch (FileNotFoundException e) {
		// 	e.printStackTrace(); // Handle the exception by printing the stack trace
		// }
	}
}
  ```

- ##### Solved 6:
```java 
package day10;

import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class ExceptionHandlingDemo2 {

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

- ##### Solved 7: 
 ```java
package com.fssa.learnJava.fop.day10andday11;

import java.io.FileNotFoundException;
import java.io.FileReader;

/**
 * Class for demoing Checked vs UncheckedException
 * 
 * @author BharathwajSoundarara
 *
 */
public class CheckedVsUncheckedExceptionDemo {
	static int divider(int a, int b) throws ArithmeticException {
		try {
			int c = a / b; // if b is zero
			return c;
		} catch (ArithmeticException ex) {
			throw ex;
		}
	}

	static void fileHandlerDemo(String fileName) throws FileNotFoundException {
		try {
			// This line may throw a FileNotFoundException
			FileReader fileReader = new FileReader(fileName);
		} catch (FileNotFoundException e) {
			throw e; // Handle the exception by printing the stack trace
		}
	}

	public static void main(String[] args) {
		try {
			Integer.parseInt("20");// Throws and unchecked NumberFormatException
			divider(8, 0); // Should throw an ArithmeticException
			fileHandlerDemo("hello.nothing");

		}
		// NumberFormatException is not caught but yet the
		// compiler is not throwing any error
		catch (ArithmeticException ex) {
			System.out.println("Catching the error in main method: " + ex.getMessage());
			ex.printStackTrace();
		}

		// If the below catch is removed the compiler will throw
		// an error line 35 since FileNotFoundException is
		// a Checked Exception
		catch (FileNotFoundException ex) {
			System.out.println("Handling only FNFE");
		} finally {
			System.out.println("Exception Introduction is completed");
		}
	}

}
```
- ##### Solved 8:
```java
package day11.solved;

import java.io.FileNotFoundException;
import java.io.FileReader;

public class CompileTimeExceptionDemo2 {

	public static void main(String[] args) throws FileNotFoundException {
		// TODO Auto-generated method stub
		Filenotfoundexception f = new Filenotfoundexception();
		try {
			f.filenotfound();
		} catch (FileNotFoundException e) {
			System.out.println("File not exists");
//			e.printStackTrace(); // Handle the exception by printing the stack trace
		}

	}

	public void filenotfound() throws FileNotFoundException {
		try {
			FileReader fileReader = new FileReader("example.txt"); // This line may throw a FileNotFoundException
			System.out.println("Line 23");

		} catch (FileNotFoundException e) {
			System.out.println("line 26");
			throw new FileNotFoundException("Thrown exception");
			// e.printStackTrace(); // Handle the exception by printing the stack trace
		}
		System.out.println("END");

	}

}
```
- ##### Solved 9:
    
    ```java
   public class DoSomething {
   public void go() {
     System.out.print("A");
	   try {
	      stop();
	   } catch (ArithmeticException e) {
	      System.out.print("B");
	   } finally {
	      System.out.print("C");
	   }
     System.out.print("D");
   }
   
    public void stop() {
      System.out.print("E");
      Object x = null;
      x.toString();
      System.out.print("F");
    }
   
    public static void main(String[] args) {
      new DoSomething().go();
    }
}
    ```






### Practice


1.Read two integers totalMarks and noOfSubjects. Find the overall average (totalMarks/noOfSubjects) . How will you handle the case when noOfSubjects is 0
```java
Scanner s = new Scanner(System.in);
System.out.println("Enter your Number: ");
int intStr = s.nextInt();
```

2.Write a code to read a String using the below lines
```java
Scanner s = new Scanner(System.in);
System.out.println("Enter your Integer: ");
String intStr = s.nextLine();
```
and loop it until the user enters valid integer. Please use try and catch clause and catch NumberFormatException thrown by Integer.parseInt method

3.Complete the below code as per instructions given the comments:
```java
class UserAccount {

	public static void validateUsername(String username) throws IllegalArgumentException {
		if (username == null) {
			// throw an Illegal Argument Exception 
			// error message "Invalid Username"
		}

		if (username.length() < 8) {
			// throw an Illegal Argument Exception  
			// with message "Username must have atleast 8 chars";
		}
	}
	
	public static void validateAge(int age)  {
		// Add your code here to validate 
		// Throw an IllegalArgumentException
		// With error msg "Invalid age"
	}
}

public class IllegalArgumentExceptionPracticeCode {

	public static void main(String[] args) {
// Fix the compiler Errors as well after removing the 
       //valid lines of code
		String username = "n";

//		try {
			UserAccount.validateUsername(username);
			// Add code to validate age
			//UserAccount.validateAge();
	//		} catch ( e) { 
//			System.out.println(e.getMessage());
//			e.printStackTrace();
//		}

	}

}
```
4. Add a finally clause in the above code and add a code **System.out.println(”Program completes”)** and check your output when you send valid and invalid values to the appropriate methods

5. What is printed besides the stack trace caused by the NullPointerException from line 16? Think and answer as a comment in the code snippet without running the code, then run the code and verify the answer.
```java
public class DoSomething {
   public void go() {
     System.out.print("A");
	   try {
	      stop();
	   } catch (ArithmeticException e) {
	      System.out.print("B");
	   } finally {
	      System.out.print("C");
	   }
     System.out.print("D");
   }
   
    public void stop() {
      System.out.print("E");
      Object x = null;
      x.toString();
      System.out.print("F");
    }
   
    public static void main(String[] args) {
      new DoSomething().go();
    }
}
```
-A.AE
-B.AEBCD
-C.AEC
-D.AECD
-E.No output appears other than the stack trace.

Additional Practice:
1.Which of the following statements are true? (Choose all that apply)
A. Runtime exceptions are the same thing as checked exceptions.
B. Runtime exceptions are the same thing as unchecked exceptions.
C. You can declare only checked exceptions.
D. You can declare only unchecked exceptions.
E. You can handle only Exception subclasses.

Answer: 

B. Runtime exceptions are also known as unchecked exceptions. They are allowed
to be declared, but they don’t have to be. Checked exceptions must be handled or
declared. Legally, you can handle java.lang.Error subclasses, but it’s not a good idea

2. Which of the following pairs fill in the blanks to make this code compile? (Choose all that
apply)
7: public void ohNo() _____ Exception {
8: _____________ Exception();
9: }
A. On line 7, fill in throw
B. On line 7, fill in throws
C. On line 8, fill in throw
D. On line 8, fill in throw new
E. On line 8, fill in throws
F. On line 8, fill in throws new
    
    Answer: 
    
    B, D. In a method declaration, the keyword throws is used. To actually throw an
    exception, the keyword throw is used and a new exception is created.

3. When is it compulsory to add a finally block in a regular try statement (not a try-with-resources)?
A. Never.
B. When the program code doesn’t terminate on its own.
C. When there are no catch blocks in a try statement.
D. When there is exactly one catch block in a try statement.
E. When there are two or more catch blocks in a try statement.
    
    Answer: 
    
    C. A try statement is required to have a catch clause and/or finally clause. If it goes
    the catch route, it is allowed to have multiple catch clauses

4. What will happen if you add the statement **System.out.println(5 / 0):** to a working main() method?
A. It will not compile.
B. It will not run.
C. It will run and throw an ArithmeticException.
D. It will run and throw an IllegalArgumentException.
E. None of the above.
    
    Answer: 
    
    C. The compiler tests the operation for a valid type but not a valid result, so the code will still compile and run. At runtime, evaluation of the parameter takes place before passing it to the print() method, so an ArithmeticException object is raised.

5. Which of the following are true? (Choose all that apply)
A. Checked exceptions are allowed to be handled or declared.
B. Checked exceptions are required to be handled or declared.
C. Errors are allowed to be handled or declared.
D. Errors are required to be handled or declared.
E. Runtime exceptions are allowed to be handled or declared.
F. Runtime exceptions are required to be handled or declared.
    
    Answer: 
    
    A, B, C, E. Checked exceptions are required to be handled or declared. Runtime
    exceptions are allowed to be handled or declared. Errors are allowed to be handled or
    declared, but this is bad practice

6.What is the output of the following program?
```java
1: public class Laptop {
2: public void start() {
3: try {
4: System.out.print("Starting up ");
5: throw new Exception();
6: } catch (Exception e) {
7: System.out.print("Problem ");
8: System.exit(0);
9: } finally {
10: System.out.print("Shutting down ");
11: }
12: }
13: public static void main(String[] args) {
14: new Laptop().start();
15: } }
```
A. Starting up

B. Starting up Problem

C. Starting up Problem Shutting down

D. Starting up Shutting down

E. The code does not compile.

F. An uncaught exception is thrown

Answer: 

B. The main() method invokes start on a new Laptop object. Line 4 prints Starting
up; then line 5 throws an Exception. Line 6 catches the exception, line 7 prints
Problem, and then line 8 calls System.exit, which terminates the JVM. The finally
block does not execute because the JVM is no longer running.

7.What is printed besides the stack trace caused by the NullPointerException from line 16?
```java
1: public class DoSomething {
2: public void go() {
3: System.out.print("A");
4: try {
5: stop();
6: } catch (ArithmeticException e) {
7: System.out.print("B");
8: } finally {
9: System.out.print("C");
10: }
11: System.out.print("D");
12: }
13: public void stop() {
14: System.out.print("E");
15: Object x = null;
16: x.toString();
17: System.out.print("F");
18: }
19: public static void main(String[] args) {
20: new DoSomething().go();
21: }
22: }
```
A. AE

B. AEBCD

C. AEC

D. AECD

E. No output appears other than the stack trace.

Answer: 

C. The main() method invokes go and A is printed on line 3. The stop method is
invoked and E is printed on line 14. Line 16 throws a NullPointerException, so stop
immediately ends and line 17 doesn’t execute. The exception isn’t caught in go, so the
go method ends as well, but not before its finally block executes and C is printed on
line 9. Because main() doesn’t catch the exception, the stack trace displays and no further output occurs, so AEC was the output printed before the stack trace.

8.What is the output of the following snippet, assuming a and b are both 0?
```java
public class ExceptionPractice {

	public static void main(String[] args) {
		ExceptionPractice e = new ExceptionPractice();
		System.out.println(e.divide(0, 0));
	}

	public int divide(int a, int b) {
		try {
			return a / b;
		} catch (Exception e) {
			return -2;
		}
		catch (RuntimeException e) {
			return -1;
		} catch (ArithmeticException e) {
			return 0;
		} finally {
			System.out.print("done");
		}
	}
}
```
A. -1
B. 0
C. done-1
D. done0
E. The code does not compile.
F. An uncaught exception is thrown.

Answer: 

E. The order of catch blocks is important because they’re checked in the order they
appear after the try block. Because ArithmeticException is a child class of RuntimeException, the catch block on line 7 is unreachable. (If an ArithmeticException is
thrown in try try block, it will be caught on line 5.) Line 7 generates a compiler error
because it is unreachable code.