---
title: Day 4 - Inheritance Part 1
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

- #### Solved 1: Single inheritance, extends

```java
package fssa.coreJava.day04;

public class Animal {
	private int age;

	public int getAge() {
		return age;
	}

	public void setAge(int age) {
		this.age = age;
	}
}
```

```java
package fssa.coreJava.day04;

public class Lion extends Animal {  // extends keyword use to inherit variables and methods from Animal
	private void roar() {
		System.out.println("The " + getAge() + " year old lion says: Roar!");
	}

	public static void main(String[] args) {
		Lion simba = new Lion();
		simba.setAge(10); // setAge() method was not defined in Lion; it is inherited from Animal
		simba.roar();
	}
}
```

- #### Solved 2: The this and super keywords

```java
package fssa.coreJava.day04.inheritanceDemo2;

/**
 * @author Vinit Gore
 *
 **/
public class Animal {
	private int age;
	private String name;

	public Animal(String name) {
		System.out.println("Calling Parent Constructor");
		this.name = name;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getAge() {
		return age;
	}

	public void setAge(int age) {
		this.age = age;
	}
}
```

```java
package fssa.coreJava.day04.inheritanceDemo2;

/**
 * @author Vinit Gore
 *
 **/
public class Lion extends Animal {

	public Lion(String name) {
		super(name);		// Calling the constructor of Animal class
		System.out.println("Calling Child Constructor");
	}

	private void roar() {
		System.out.println("The " + getAge() + " year old " + getName() + " says: Roar!");
	}

	public static void main(String[] args) {
		Lion simba = new Lion("Simba");
		simba.setAge(10); // setAge() method was not defined in Lion; it is inherited from Animal
		simba.roar();
	}
}
```

- #### Solved 3: Abstract Class, Function Overriding and final

```java
package com.fssa.learnJava.corejava.day04;

public abstract class Polygon {
	protected int numberOfSides;

	public Polygon (int numberOfSides) throws Exception {
		if (numberOfSides < 3) {
			throw new Exception("Invalid number of sides to create a polygon ");
		}
		else {
			this.numberOfSides = numberOfSides;
		}
	}


	public abstract double calculateArea();
}
```

```java
package com.fssa.learnJava.corejava.day04;

/**
 * @author BharathwajSoundarara
 *
 */
public class Rectangle extends Polygon {

	protected double length;
	protected double breadth;

	public Rectangle(double length, double breadth) throws Exception {
		super(4);
		if(length <= 0 || breadth <= 0) {
			throw new Exception("Invalid dimensions for a rectangle");
		}
		this.length = length;
		this.breadth = breadth;
	}

	@Override
	public double calculateArea() {
		// TODO Auto-generated method stub
		return this.length * this.breadth;
	}

	public int getNumberOfSides() {
		return super.numberOfSides;
	}

}
```

```java
package com.fssa.learnJava.corejava.day04;

/**
 * @author VinitGore *
 */

public class Square extends Rectangle {

	public Square(double side_length) throws Exception {
		super(side_length, side_length);
	}

}
```

```java
package fssa.coreJava.day04;

public class AnotherClass extends Square {  // This line will give compiler error

}
```

- #### Solved 4: Add toString method

Without **toString** method:

```java
class Account3 {

	private String accNo;

	private String name;

	private double balance;

	// Default Constructor
	public Account3() {

	}

	// Creating a Constructor which accepts all the attributes: Constructor
	// Overloading
	public Account3(String accNo, String name, double balance) {
		this.accNo = accNo;
		this.name = name;
		this.balance = balance;
	}

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


}
```

Testing:

```java
public class ToStringDemo {
	public static void main(String[] args) {
		// create Account using Setter methods and Default constructor
		Account3 acct1 = new Account3();
		acct1.setAccNo("A101");
		acct1.setName("Naresh");
		acct1.setBalance(1000);

		System.out.println(acct1);
	}
}
```

What is the output when you run the test?
With **toString** method:

```java
class Account3 {

	private String accNo;

	private String name;

	private double balance;

	// Default Constructor
	public Account3() {

	}

	// Creating a Constructor which accepts all the attributes: Constructor
	// Overloading
	public Account3(String accNo, String name, double balance) {
		this.accNo = accNo;
		this.name = name;
		this.balance = balance;
	}

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

	@Override
    public String toString() {
        return "Account [accNo=" + accNo + ", name=" + name + ", balance="  + balance + "]";
    }

}
```

What is the output when you run the test after adding the toString method?

@Override - annotation to be covered during Inheritance

### Practice

Question: Create a Circumference method to Polygon abstract class and implement it in the

1. Rectangle Class from solved example
2. RightAngledTriangle Class from solved example
