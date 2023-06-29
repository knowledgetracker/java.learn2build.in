---
title: Day 09 - Arrays
description: 
date: 2023-06-13
duration: 3 hrs
solved: 0
practice: 0
hots: 0
tags:
  - java
layout: layouts/post.njk
---


### Solved
- #####  Solved 1: Integer Array

```java
  package day09;

  public class ArrayDemo {

    public static void main(String[] args) {

      // Array with a length of 3
      int[] marks = new int[3];

      // assign marks in the array
      marks[0] = 50;
      marks[1] = 60;
      marks[2] = 70;

      
      // find how many items in the array
      System.out.println("Array size is: " + marks.length);
      
    
      // Iterate array using for loop
      for (int i = 0; i < marks.length; i++) {
        int m = marks[i];
        System.out.println("Mark is: " + m);
      }

    }

  }
```
- ##### Solved 2: String Array
```java
  package day09;

  public class ArrayDemo2 {

    public static void main(String[] args) {

      // Array with a length of 3
      String[] names = new String[3];

      // assign marks in the array
      names[0] = "Surya";
      names[1] = "Vijay";
      names[2] = "Ajith";

      // find how many items in the array
      System.out.println("Array size is: " + names.length);
      
      // Iterate array using for loop
      for (int i = 0; i < names.length; i++) {
        String m = names[i];
        System.out.println("Mark is: " + m);
      }

    }

  }

```


- ##### Solved 3: 
``` java
  package day09;

  public class ArrayDemo3 {

    public static void main(String[] args) {

      // Array with a length of 3
      String[] names = new String[3];

      // assign marks in the array
      names[0] = "Surya";
      names[1] = "Vijay";
      names[2] = "Ajith";

      // find how many items in the array
      System.out.println("Array size is: " + names.length);

      // Iterate array using for loop
      for (int i = 0; i < names.length; i++) {
        String name = names[i];
        System.out.println("Mark is: " + name);
      
        if(  name.trim().equals("Vijay") ) {
          System.out.println("Match found");
          break;
        }
      
      }

    }

  }
```

- ##### Solved 4: Array Declarations
```java
  package day09;

  public class ArrayDemo4 {

    public static void main(String[] args) {

      // Different ways to declare arrays

      // 1
      int[] marks = new int[3];
      // assign marks in the array
      marks[0] = 50;
      marks[1] = 60;
      marks[2] = 70;
      // marks[3] = 80; //ArrayIndexOutOfBoundsException


      // 2
      // int[] markss = new int[] { 50, 60, 70 };



      // 3
      // int[] marksss = { 50, 60, 70 };

      // Iterate array using for loop
      for (int i = 0; i < marks.length; i++) {
        int m = marks[i];
        System.out.println("Mark is: " + m);
      }

    }

  }
```

- ##### Solved 5: Arrays of different datatypes: String, char and Object
``` java
  package Day09.Solved;
  /*
  @VinitGore
  */
  public class ArrayDemo2 {

    String name;
    int age;

    public static void main(String[] args) {
      // TODO Auto-generated method stub
      String[] names = new String[3];


      for(int i=0; i<names.length;i++) {
        String m = names[i];
        System.out.println("The name is "+m);
      }

      System.out.println("Total Array length is " + names.length);

      for(int i=0; i<names.length;i++) {
        String m = names[i];
        System.out.println("The name is "+m);
      }

  //		Character Array

      char[] letters = new char[3];

      for(int i=0; i<letters.length;i++) {
        char m = letters[i];
        System.out.println("The letter is "+m);
        System.out.println((int)m);
      }

      letters[0] = 'F';
      letters[1] = 'A';
      letters[2] = 'N';



      for(int i=0; i<letters.length;i++) {
        char m = letters[i];
        System.out.println("The letter is "+m);
        System.out.println("The integer value is: " +(int)m);
      }

  //		// object Array
      ArrayDemo2[] details = new ArrayDemo2[3];  // create array of objects
      System.out.println(Arrays.toString(details));
      System.out.println(details[0]);



      // creating objects
      ArrayDemo2 student1 = new ArrayDemo2();
      student1.name ="Batman";
      student1.age =16 ;
      ArrayDemo2 student2 = new ArrayDemo2();
      student2.name ="Superman";
      student2.age = 17;
      ArrayDemo2 student3 = new ArrayDemo2();
      student3.name ="Spiderman";
      student3.age = 48;

      // assigning the objects into Array
      details[0] = student1;
      details[1] = student2;
      details[2] = student3;

      // loop for printing the value
      for(ArrayDemo2 e : details) {
        System.out.println(e);
        System.out.println("Student name is " + e.name + " he is " + e.age + " yrs old ");
      };


    }
  }
  ```

- ##### Solved 6:  Write a Java program to find the sum of all elements in an array.
```java 
  package day09;

  public class ArraySum {

      public static void main(String[] args) {
          int[] array = { 1, 2, 3, 4, 5 };
          int sum = 0;

          for (int i = 0; i < array.length; i++) {
              sum += array[i];
          }

          System.out.println("Sum: " + sum);
      }

  }
```

- ##### Solved 7: Sum of all array elements using for each.
 ```java
    /**
   * Class to demo Iterating an array using for each syntax
   * 
   * @author BharathwajSoundarara
   *
   */
  public class ForEachArrayDemo {
    public static void main(String[] args) {
      int[] arr = { 6, 19, 10 };
      int sum = 0;
      // For Each Syntax for looping with each element
      for (int element : arr) {
        sum += element; // Summing up each element
        System.out.println("Added element: " + element);
      }
      System.out.println("Sum of elements: " + sum);
    }
  }
```
- ##### Solved 8:Write a Java program to **count the number of even elements** in an array.
```java
  package day09;

  public class ArrayCountEven {
      public static void main(String[] args) {
          int[] array = { 2, 5, 8, 3, 10, 6 };
          int count = 0;

          for (int i = 0; i < array.length; i++) {
              if (array[i] % 2 == 0) {
                  count++;
              }
          }

          System.out.println("Number of even elements: " + count);
      }

  }
```
- ##### Solved 9:- Write a Java program to **check if an element exists in an array**.
    
```java
    package day09;
    
    public class ArrayContains {
        public static void main(String[] args) {
            int[] array = { 3, 6, 1, 8, 4 };
            int searchElement = 8;
            boolean found = false;
    
            for (int i = 0; i < array.length; i++) {
                if (array[i] == searchElement) {
                    found = true;
                    break;
                }
            }
    
            if (found) {
                System.out.println("Element found!");
            } else {
                System.out.println("Element not found!");
            }
        }
    }
    ```

- ##### Solved 10: Illustrating how to access a multidimensional array.
```java
  /**
   * Program to demonstrate now to declare and access
   * a Multidimensional array
   * @author BharathwajSoundarara
   *
   */
  public class DeclaringMultiDimArrayDemo {
    public static void main(String[] args) {
      int[][] twodArray = { { 1, 2, 3 }, 
                  { 4, 5, 6 }, 
                  { 7, 8, 9 } };

      // Accessing twodArray

      System.out.println("Printing the first "
          + "element in the first row "
          + twodArray[0][0]);
      
      System.out.println("Accessing the third "
          + "element in the Second row "
          +  twodArray[1][2]);
      
      // Creating a dynamic multi-dimentional array
      
      int[][] dynamic2dArray = new int[5][5];
      
      // Setting the first element in the first row as 5
      dynamic2dArray[0][0] = 5;
      

    }
  }
  ```




### Practice

1. Write a Java program to find the average of elements in an array.
2. Write a Java program that takes an array of integers as input and finds the maximum and minimum values in the array. Print both the maximum and minimum values.
3. Write a Java program that takes an array of floating-point numbers as input and calculates the average of the numbers. Print the average value.
4. Write a Java program that takes an array of strings as input and reverses the order of elements in the array. Print the reversed array.



