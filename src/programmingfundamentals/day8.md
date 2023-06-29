---
title: Day 08 - Looping Statements
description: 
date: 2023-06-12
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
  package day08;

  public class LoopingStatmentDemo {

    public static void main(String[] args) {

      for (int i = 1; i <= 10; i++) {
        System.out.println("The value of i is : " + i);
      }

    }

  }
```
- ##### Solved 2: 
```java
  package day08;

  public class LoopingStatmentDemo2 {

    public static void main(String[] args) {

      int i = 0;

      while (i <= 10) {
        System.out.println("The value of i is: " + i);
        i++;
      }

    }

  }

```


- ##### Solved 3: 
``` java
  package day08;

  public class LoopingStatmentDemo3 {

    public static void main(String[] args) {

      int i = 0;

      do {
        System.out.println("The value of i is:" + i);
        i++;
      } while (i <= 10);

    }

  }
```

- ##### Solved 4: 
```java
    /**
     * Class Created for demoing additional conditions and truthTable
     * @author BharathwajSoundarara
     *
     */
    class Rat {
      int roomInBelly = 5;

      public void eatCheese(int bitesOfCheese) {
        // Keep eating as long as there is roomInBelly and some cheese
        // is left
        while (bitesOfCheese > 0 && roomInBelly > 0) {
          bitesOfCheese--;
          roomInBelly--;
        }
        System.out.println(bitesOfCheese + " pieces of cheese left");
      }
      public void showRoomInBelly() {
        System.out.println("Room in belly: " + roomInBelly);
      }
    }

    /**
     * Class for creating an instance of a Rat Class
     * @author BharathwajSoundarara
     *
     */
    public class RatDemo {
      public static void main(String[] args) {
        Rat rat = new Rat();
        rat.roomInBelly = 5;
        rat.eatCheese(10);
        // Calling Belly Capacity
        rat.showRoomInBelly();
      }
    }
```

- ##### Solved 5:
``` java
  int n = 35;
  int result = 1;
  while (n > 0)
  {
      int d = n % 10;
      result *= d;
      n /= 10;
  }
  System.out.println(result);
```
- ##### Solved 6:
  ``` java
    int count = 0;
  /* missing loop header */
  {
      if (count % 2 == 0)
      {
          System.out.println(count);
      }
      count++;
  }
  ```



### Practice


1. Write a Java program that prints the first 10 natural numbers using a `for` loop.
2. Write a Java program that prints the first 10 natural numbers in reverse order using a `while` loop.
3. Write a Java program that prints the first 10 even numbers using a `do-while` loop.
4. Write a Java program that calculates the sum of first 10 natural numbers and prints the result.
5. Write a Java program that checks whether a predefined number (for example, 29) is a prime number or not, using a for loop. A prime number is a number that has exactly two distinct positive divisors: 1 and itself.
6. (Vinit) Rewrite using `for` loop:
  
```java
  public class Test1
  {
      public static void main(String[] args)
      {
          int x = 5;
          while (x > 0)
          {
              System.out.println(x);
              x = x - 1;
          }
      }
  }
   ```
7.Rewrite using while loop: 
```java
  public class Test1
  {
      public static void main(String[] args)
      {
          for (int x = 1; x <= 10; x++)
              System.out.println(x);
      }
  }
```
8.The following code should print the values from 1 to 10 (inclusive) but has errors. Fix the errors so that the code works as intended. 

```java
  public class Test1
  {
      public static void main(String[] args)
      {
          int x = 1;
          while (x < 10)
          {
              System.out.println(x);
          }
      }
  }
```
 Additional Practice: Refer [here](https://runestone.academy/ns/books/published/csawesome/Unit4-Iteration/topic-4-8-practice-coding.html?mode=browsing).

```


