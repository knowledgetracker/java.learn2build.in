---
title: Day 1 - Class & Objects
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

- #### Task 1: Creating a Book

```java
/**
 * Solved Example for day 1
 * @author BharathwajSoundarara
 *
 */
class Book {
	public String title;
	public String author;
	public double price;

	public void printBookDetails() {
		System.out.println("Title: " + title);
		System.out.println("Author: " + author);
		System.out.println("Price: " + price);
	}


}

public class TestBook {
	public static void main(String[] args) {
		Book book1 = new Book();

		book1.title = "Harry Potter";
		book1.author = "JK Rowling";
		book1.price = 400;
		System.out.println("------------Book1 Details---------");
		book1.printBookDetails();

		Book book2 = new Book();

		book2.title = "Lord of the Rings";
		book2.author = "JRR Tolkien";
		book2.price = 800;
		System.out.println("------------Book2 Details---------");
		book2.printBookDetails();


	}
}
```

- #### Task 2: Car Example

```java
package com.fssa.learnJava.corejava.day01;


/**
* In the real world, you'll often find many individual objects all of the same
* kind. There may be thousands of other bicycles in existence, all of the same
* make and model. Each car was built from the same set of blueprints and
* therefore contains the same components. In object-oriented terms, we say that
* your Car is an instance of the class of objects known as Cars. A
* class is the blueprint from which individual objects are created.
*
* @author BharathwajSoundarara
*
*/
class Car {

	public int speed = 0;
	public int gear = 1;

	public void changeGear(int newValue) {
		gear = newValue;
	}

	public void speedUp(int increment) {
		speed = speed + increment;
	}

	public void applyBrakes(int decrement) {
		speed = speed - decrement;
	}

	public void printStates() {
		System.out.println(" speed:" + speed + " gear:" + gear);
	}
}

/**
* Here's a CarDemo class that creates two separate Car objects and
* invokes their methods:
*
* @author BharathwajSoundarara
*
*/
public class CarDemo {
	public static void main(String[] args) {

		// Create a Car object

		Car car1 = new Car();
		// Invoke methods on
		// those objects
		car1.speedUp(10);
		car1.changeGear(2);
		car1.printStates();

		Car car2 = new Car();

		car2.speedUp(10);
		car2.changeGear(2);
		car2.speedUp(10);
		car2.changeGear(3);
		car2.printStates();
	}
}

```

- #### Task 3: Comparing two objects

```java
 /**


- Solved Example for day 1
- @author BharathwajSoundarara
- \*/
 class Movie {
 public String title;

}

public class TestBookComparison {
public static void main(String[] args) {
Movie movie1 = new Movie();
movie1.title = "Harry Potter";
Movie movie2 = new Movie();
movie2.title = "Lord of the Rings";
// Each object will be Stored in a separate memory location
// so it will print false
System.out.println(movie1 == movie2);
}
}

```

- #### Task 4: Static variable vs instance variable

```java
public class MyClass {
    // Declare a static variable
    public static int staticVariable;

    public static void main(String[] args) {
        // Access the static variable using the class name
        MyClass.staticVariable = 10;
        System.out.println(MyClass.staticVariable);
    }
}
```

```java
public class MyClass {
    // Declare a static variable
    public static int staticVariable;

    public static void main(String[] args) {
        // Access the static variable using the class name
        MyClass.staticVariable = 10;
        System.out.println(MyClass.staticVariable);
    }
}
```

### Additional Example

- #### Task 1: Creating Dog class and its objects

```java
public class Dog {
    // Attributes
    private boolean hasDots;
    private String color;

    // Constructor
    public Dog(boolean hasDots, String color) {
        this.hasDots = hasDots;
        this.color = color;
    }

    // Getters and setters
    public boolean hasDots() {
        return hasDots;
    }

    public void setHasDots(boolean hasDots) {
        this.hasDots = hasDots;
    }

    public String getColor() {
        return color;
    }

    public void setColor(String color) {
        this.color = color;
    }

		public void speak() {
        System.out.println("Woof!");
    }

    // Main method to create Dog objects
    public static void main(String[] args) {
        // Create two Dog objects
        Dog dog1 = new Dog(true, "purple");
        Dog dog2 = new Dog(true, "blue");

        // Print the attributes of each Dog
        System.out.println("Dog 1:");
        System.out.println("Has Dots: " + dog1.hasDots());
        System.out.println("Color: " + dog1.getColor());
				System.out.println("Speaks: " + dog1.speak());

        System.out.println("Dog 2:");
        System.out.println("Has Dots: " + dog2.hasDots());
        System.out.println("Color: " + dog2.getColor());
				System.out.println("Speaks: " + dog1.speak()
    }
}
```

- #### Task 2: Adding the Dog class to a package

```java
package day01_classes_and_objects;

public class Dog {
   // Attributes
   private boolean hasDots;
   private String color;

   // Constructor
   public Dog(boolean hasDots, String color) {
       this.hasDots = hasDots;
       this.color = color;
   }

   // Getters and setters
   public boolean hasDots() {
       return hasDots;
   }

   public void setHasDots(boolean hasDots) {
       this.hasDots = hasDots;
   }

   public String getColor() {
       return color;
   }

   public void setColor(String color) {
       this.color = color;
   }

   // Main method to create Dog objects
   public static void main(String[] args) {
       // Create two Dog objects
       Dog dog1 = new Dog(true, "purple");
       Dog dog2 = new Dog(true, "blue");

       // Print the attributes of each Dog
       System.out.println("Dog 1:");
       System.out.println("Has Dots: " + dog1.hasDots());
       System.out.println("Color: " + dog1.getColor());

       System.out.println("Dog 2:");
       System.out.println("Has Dots: " + dog2.hasDots());
       System.out.println("Color: " + dog2.getColor());
   }
}
```

### Practice

1. Create a class for Cat, similar to the Dog class.

Dog Class Code:

```java
public class Dog {
    // Attributes
    private boolean hasDots;
    private String color;

    // Constructor
    public Dog(boolean hasDots, String color) {
        this.hasDots = hasDots;
        this.color = color;
    }

    // Getters and setters
    public boolean hasDots() {
        return hasDots;
    }

    public void setHasDots(boolean hasDots) {
        this.hasDots = hasDots;
    }

    public String getColor() {
        return color;
    }

    public void setColor(String color) {
        this.color = color;
    }

		public void speak() {
        System.out.println("Woof!");
    }

    // Main method to create Dog objects
    public static void main(String[] args) {
        // Create two Dog objects
        Dog dog1 = new Dog(true, "purple");
        Dog dog2 = new Dog(true, "blue");

        // Print the attributes of each Dog
        System.out.println("Dog 1:");
        System.out.println("Has Dots: " + dog1.hasDots());
        System.out.println("Color: " + dog1.getColor());
				System.out.println("Speaks: " + dog1.speak());

        System.out.println("Dog 2:");
        System.out.println("Has Dots: " + dog2.hasDots());
        System.out.println("Color: " + dog2.getColor());
				System.out.println("Speaks: " + dog1.speak()
    }
}
```

Get the following output:

```java
Cat 1:
Age: 4
Color: White
Speaks: Meow!
Cat 2:
Age: 3
Color: Black
Speaks: Meow!
```

2. Make changes in this code so that it gets compiled and generates the output:

```java

public class AccessModifier {
	private String a = "a";
	private String b = "b";
	private String c = "c";
	private static String d = "d";

	public static void main(String[] args) {
		System.out.println(a);
		System.out.println(b);
		System.out.println(c);
		System.out.println(d);
	}
}
```
