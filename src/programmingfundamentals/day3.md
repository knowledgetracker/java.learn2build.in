---
title: Day 03 - Datatypes
description: 
date: 2023-06-05
duration: 3 hrs
solved: 0
practice: 0
hots: 0
published: false
tags:
  - java
layout: layouts/post.njk
---


### Solved
- #####  Solved 1: Datatype

```java
  package day03;

  public class DatatypeDemo {

    public static void main(String[] args) {
    
      int a = 10;
      System.out.println("a = " + a);
      
      float b = 10.9f;
      System.out.println("b = "+ b);
      
      double c = 10.999354399999999d;
      System.out.println("c = " + c);
      
      long d = 9876543210l;
      System.out.println("d = "+ d);
      
      char e = 'h';
      System.out.println("e = "+ e);
      
    }
  }
```
- ##### Solved 2: Data Conversion
```java
  package day03;

  public class DataConversionDemo {

    public static void main(String[] args) {

      int three = Integer.parseInt("3");
      System.out.println("three = " + three);

      float percentage = Float.parseFloat("98.3");
      System.out.println("percentage= " + percentage);

      double pi = Double.parseDouble("3.14");
      System.out.println("pi = " + pi);

      long number = Long.parseLong("9876543210");
      System.out.println("number = " + number);
    }
  }
```

- ##### Solved 3: Maximum values 
```java
  public class DataTypeMaxValues {
    public static void main(String[] args) {
      System.out.println("Byte range: " + Byte.MIN_VALUE + " to "+ Byte.MAX_VALUE );
      System.out.println("Short Int range: " + Short.MIN_VALUE + " to "+ Short.MAX_VALUE );
      
      System.out.println("Integer range: " + Integer.MIN_VALUE + " to " + Integer.MAX_VALUE);
      System.out.println("Float range: " + Float.MIN_VALUE + " to " + Float.MAX_VALUE);
      System.out.println("Double range: " + Double.MIN_VALUE + " to " + Double.MAX_VALUE);
      
      //Overflow Runtime exceptions will be talked during exception handling	
    }
  }
```

### Practice

- Write a Java program that declares different types of variables and print their values. eg. Student name, isStudent, age, percentage, Gender (in char), height (in double).
- write a program to convert `String` data type into other data types.



