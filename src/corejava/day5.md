---
title: Day 5 - Inheritance and Composition
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

- #### Solved 1: Interface and Polymorphism

```java
package com.fssa.learnJava.corejava.day05;

/**
 * @author BharathwajSoundarara
 *
 */
public interface Polygon {

	public double area(double a, double b);
}
```

```java
package com.fssa.learnJava.corejava.day05;

public class Rectangle implements Polygon {

	@Override
	public double area(double a, double b) {
		System.out.println("Calculating Rectangle area");
		return a*b;
	}

}
```

```java
package com.fssa.learnJava.corejava.day05;

public class RightAngledTriangle implements Polygon {

	@Override
	public double area(double a, double b) {
		System.out.println("Calculating RightAngledTriangle area");
		return (0.5 * a * b);
	}

}
```

```java
/**
 *
 */
package com.fssa.learnJava.corejava.day05;

/**
 * @author BharathwajSoundarara
 *
 */
public class TestInfPolygon {

	/**
	 * @param args
	 */
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Polygon p = new Rectangle();
		double area = p.area(5, 6);
		System.out.println("Calculated Area: " + area);

		p = new RightAngledTriangle();

		area = p.area(5,  6);

		System.out.println("Newly calculated Area: " + area);

	}

}
```

- #### Solved 2: Has A relationship example

```java
/**
 * Engine class
 * @author BharathwajSoundarara
 *
 */
class Engine {

	String capacity;

	public Engine(String capacity) {
		this.capacity = capacity;
	}

	public void printEngineDetails() {
		System.out.println("Engine Capacity: " + this.capacity);
	}
}

/**
 * Car with just the engine and maker details
 * @author BharathwajSoundarara
 *
 */
class Car {
	Engine engine;
	String maker;

	public Car(String maker, Engine engine) {
		this.engine = engine;
		this.maker = maker;
	}

	public void printCarDetails() {
		System.out.println("Maker: " + maker);
		this.engine.printEngineDetails();
	}
}

public class HasARelDemo {
	public static void main(String[] args) {
		// We need make the engine before making a car
		Engine engine1 = new Engine("1000cc");

		// Creating a maruti car
		Car marutiCar = new Car("Maruti", engine1);

		marutiCar.printCarDetails();

		// We need make the engine before making a car
		Engine engine2 = new Engine("1500cc");

		// Creating a benz car
		Car benz = new Car("Mercedes Benz", engine2);

		benz.printCarDetails();

	}
}
```

### Practice

Question 1: Create an implementation of the Below Interface

```java
// Change the below class to have setters and Getters and Constructors
class Account  {
	String accNo;
	double balance;

}

//Create an implementation of the below Interface
public interface ATM {
    boolean deposit(Account account, double amount);
    boolean withdraw(Account account,double amount) throws Exception;
    double getBalance();
}
```

Task 1: Create an AxisATM implementation which will have withdrawal charges of 5 rupees. If the balance is less than 5000, the withdraw method should throw and exception

Task 2: Create an IciciATM implementation which will have withdrawal charges of 10 rupees.

If the balance is less than 10000, the withdraw method should throw and exception

Implement the Deposit method which is common for all the Banks.

Question 2: Complete the below Code snippet similar to the car example.

```java

class Department {
	String deptName;
	int deptId;

}

class Student {
	String name;
	int id;
	Department department;

	// Create a constructor and assign depart and respective attributes
	// Add toString method to get the Student details.
}

// Create a main class to create a Student and Department objects
// and print the details
```
