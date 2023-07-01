---
title: Day 2 -  Function Overloading and Encapsulation
description:
date: 2023-06-14
duration: 3 hrs
solved: 0
practice: 0
hots: 0
tags:
  - corejava
layout: layouts/post.njk
---

### Solved

### Functional Overloading:

- #### Task 1: Use the same function to calculate the area of a circle and a rectangle

```java
// Method overloading in Java
public class ShapeCalculator {
		// Calculating Area for Circle
    public double calculateArea(double radius) {
        return Math.PI * radius * radius;
    }

		// Calculating Area for Rectangle
    public double calculateArea(double length, double width) {
        return length * width;
    }
}

public class Main {
    public static void main(String[] args) {
        ShapeCalculator calculator = new ShapeCalculator();
        double circleArea = calculator.calculateArea(3.5);                     // Output: 38.48451000647496
        double rectangleArea = calculator.calculateArea(4.2, 6.8);            // Output: 28.559999999999995
    }
}
```

In this example, we have a **`ShapeCalculator`** class with two **`calculateArea`** methods. The first method calculates the area of a circle based on the radius, while the second method calculates the area of a rectangle based on its length and width. By providing different parameter lists, Java allows us to differentiate between these two methods with the same name.

- #### Task 2: Function overloading for different datatypes

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }

    public String add(String a, String b) {
        return a + b;
    }
}

// Usage
Calculator calc = new Calculator();
System.out.println(calc.add(2, 3));           // Output: 5
System.out.println(calc.add(2.5, 3.7));       // Output: 6.2
System.out.println(calc.add("Hello", "World"));  // Output: HelloWorld

```

In the example above, the **`Calculator`** class has multiple **`add`** methods, each with different parameter types. Depending on the arguments passed, the appropriate **`add`** method is invoked.

### Encapsulation :

- #### Task 1: Adding Getters/Setters for Encapsulations

```java
public class Person {
    private String name;  // Private data member

    public String getName() {  // Public getter method
        return name;
    }

    public void setName(String newName) {  // Public setter method
        name = newName;
    }
}

// Usage
Person person = new Person();
person.setName("John");      // Setting the name using the setter method
String name = person.getName();  // Accessing the name using the getter method
System.out.println(name);    // Output: John

```

In the example above, the **`name`** data member is encapsulated within the **`Person`** class, and access to it is controlled through the getter and setter methods. This allows for data abstraction and protects the internal state of the object.

Reflect on how with the help of encapsulation - hiding the internal implementation details and providing controlled access to the data through methods is achieved.

- #### Task 2: Using this keyword

```java
public class Person {
    private String name;  // Private data member

    public String getName() {  // Public getter method
        return name;
    }

    public void setName(String name) {  // Public setter method
        // name = name; Wrong way to use refer the attribute of class
			this.name = name; // this Keyword used for referring current instance
    }
}

// Usage
Person person = new Person();
person.setName("John");      // Setting the name using the setter method
String name = person.getName();  // Accessing the name using the getter method
System.out.println(name);    // Output: John
```

The **`this`** keyword is used to refer to the current instance of the class, and using it can help distinguish between the instance variable **`name`** and the local variable **`name`** having the same name.

- #### Task 3: Add Getters/Setters

Create a class “BankAccount” that has accNo, name and balance as its attributes and add getter/setter methods for all attributes:

```java
public class BankAccount {

    private String accNo;
    private String name;
    private double balance;

    public String getAccNo() {
        return accNo;
    }

    public void setAccNo(String accNo) {
        this.accNo = accNo;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getBalance() {
        return balance;
    }

    public void setBalance(double balance) {
        this.balance = balance;
    }
```

Test the class using the following code:

```java
public class TestBankAccount {

    public static void main(String[] args) {

        //create Account
        BankAccount acct1 = new BankAccount();
        acct1.setAccNo("A101");
        acct1.setName( "Krishna" );
        acct1.setBalance(1000);

        System.out.println(acct1.getAccNo());
        System.out.println(acct1.getName());
        System.out.println(acct1.getBalance());
    }
}
```

### Practice

Question#1 (For Encapsulation): Create a **User** class with attribute id, name, password, emailId and create setters and getters for the same. Please note no attribute should be available publicly they should be only be accessible via the access modifiers.

Question#2: Create a logger class and utility methods (log, debug , error) and accepts different parameters

```java
public class Logger {
	public static void debug (String msg) {
		System.out.println("DEBUG: " + msg);
	}
	public static void info (String msg) {
		// TODO complete this code using the above template
	}

	public static void error (String msg) {
		// TODO complete this code using the above template
	}

	public static void debug (int num) {
		// TODO Complete this code
	}

	// Similarly write overloaded methods for error and info.
}
```
