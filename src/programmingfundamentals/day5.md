---
title: Day 05 - Objects
description: 
date: 2023-06-07
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
package day05;

public class BookDemo {

	public static void main(String[] args) {
		
		BookDemo newBook = new BookDemo();
		System.out.println(newBook);
		newBook.display();

	}
	
	public void display() {
		System.out.println("Display Method is invoked");
	}

}
```
- ##### Solved 2: 
```java
/**
 * In the real world, you'll often find many individual objects all of the same
 * kind. There may be thousands of other bicycles in existence, all of the same
 * make and model. Each bicycle was built from the same set of blueprints and
 * therefore contains the same components. In object-oriented terms, we say that
 * your bicycle is an instance of the class of objects known as bicycles. A
 * class is the blueprint from which individual objects are created.
 * 
 * @author BharathwajSoundarara
 *
 */
public class Bicycle {

	int speed = 0;
	int gear = 1;

	void changeGear(int newValue) {
		gear = newValue;
	}

	void speedUp(int increment) {
		speed = speed + increment;
	}

	void applyBrakes(int decrement) {
		speed = speed - decrement;
	}

	void printStates() {
		System.out.println(" speed:" + speed + " gear:" + gear);
	}
}


```

``java
/**
 * Here's a BicycleDemo class that creates two separate Bicycle objects and
 * invokes their methods:
 * 
 * @author BharathwajSoundarara
 *
 */
public class BicycleDemo {
	public static void main(String[] args) {

		// Create two different
		// Bicycle objects
		Bicycle bike1 = new Bicycle();
		Bicycle bike2 = new Bicycle();

		// Invoke methods on
		// those objects
		bike1.speedUp(10);
		bike1.changeGear(2);
		bike1.printStates();

		bike2.speedUp(10);
		bike2.changeGear(2);
		bike2.speedUp(10);
		bike2.changeGear(3);
		bike2.printStates();
	}
}

```
- ##### Solved 3: 
``` java
public class Animal{

		int numLegs = 4;      // initialize on declaration
		String species;
	
	
		public Animal(){
			species = "Dog";    // initialize in constructor
		}

}
```

- ##### Solved 4: 
```java
// Animal.java
public class Animal{

		int numLegs = 4;      // initialize on declaration
		String species;
	
	
		public Animal(String speciesName){
			species = speciesName;    // initialize in constructor
		}

		@Override
		public String toString() {
			String animalDetails = "{ numLengs : "+numLegs+" species: "+species+" }";
			System.out.println(animalDetails);
			return animalDetails;
		}
}


//  App.java
public class App{

	public static void main(String[] args){
		Animal dog = new Animal("Dog");
		dog.toString();
	}

}
```
- ##### Solved 5:
```java
 // Animal.java
public class Animal{

		int numLegs;      
		String species;
	
	
		public Animal(String speciesName, int noOfLegs){
			species = speciesName;    
			numLegs = noOfLegs;
		}

		@Override
		public String toString() {
			String animalDetails = "{ numLengs : "+numLegs+" species: "+species+" }";
			System.out.println(animalDetails);
			return animalDetails;
		}
}


//  App.java
public class App{

	public static void main(String[] args){
		Animal dog = new Animal("Dog", 4);
		dog.toString();

		Animal penguin = new Animal("penguin", 2);
		penguin.toString();
	}

}
```

### Practice

```
- Create a new instance of 'Student' class with methods, and print the student details in the main method.
- Create a new instance of 'Calculator' class that performs various mathematical operations.  (Addition, Sub, Multiplication & Division). Call the instance methods for addition, subtraction, multiplication and division in the main class.
```


