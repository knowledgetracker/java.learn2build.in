---
title: Day 13-17 - Additional Topics
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

**Day 13 HttpClient/JSON Library**

Exercise: Convert an JSON into an Array of Objects and vice versa. In a todo app,

do registration by accepting User attributes as a JSON
get a list of tasks as JSON.

---

**Day 14 : IO (Total 3 hrs, Solved: 2, practice: 4)**

[Solved Examples](https://www.notion.so/Solved-Examples-b7d800dd984b4ea5a8612558f1b23af9?pvs=21) (2 Questions)

[Practice Questions](https://www.notion.so/Practice-Questions-9ec5963853134d8da48d5a2131dd7697?pvs=21) (4 questions)

Serialization

- Resources

  - [CSV file read api](https://nareshkumarh.wordpress.com/2016/04/04/csv-file-read-api/)

  Recommendation: From Day 13 Mini project should starts. Its optional to cover day 13 to 17 day. Folks grabbing things quickly can do day 13 to day 17 and then start Mini project, others who find things difficult can start their mini project and if they have time do day 15 to day 17 topics

---

**Day 15, 16: Latest Features (Total 6 hrs, Solved: 0, practice: 0)**

(Some of these can be covered with the related topics covered before)

(Whenever teaching these features, show a previous feature example along with the new feature)

- JDK 5, 6, 7, 8, till 17
  - JDK 5:
    - Autoboxing/Unboxing
    - Annotations
    - ENUM
    - Variable arguments
    - Enhanced foreach loop
    - static import
    - ~~StringBuilder~~
  - JDK 7:
    - Diamond operator
    - try with resources
    - Catching multiple exceptions (Multi-catch)
  - JDK 8:
    - ~~Functional interface~~
    - ~~Lambda expressions~~
    - Streams (Can be added on Day 9 if time permits)
    - Java Time API ( LocalDate, LocalTime, LocalDateTime)
  - JDK 9:
    HTTPClient features
  - JDK 11
  - Tasks: Convert code from one version to other
  - Resource
    - [Varargs application - Marks Calculator](https://nareshkumarh.wordpress.com/2020/01/07/markcalculator/)
    - [Add multiple emails into](https://nareshkumarh.wordpress.com/2017/01/23/add-multiple-emails-in-to/)
    - [Stream example to search Array](https://nareshkumarh.wordpress.com/2016/10/16/3386/) (Arrays)
- Functional Interface (Java 8)
  - Creating a Thread using Functional Interface
- StreamAPI (Java 8)
  - Iterating Collections with Streams
- Lambda Expressions (Java 8)

  - Resources

    - [Iterate collections using lambda expression](https://nareshkumarh.wordpress.com/2016/09/17/iterate-collections-using-lambda-expression/)

    **Day 17: Threads (Total 3 hrs, Solved: 0, practice: 0)**

- Basic Introduction
  - What is Thread
  - Difference between a process and a thread
  - Different means to create a thread
- Writing thread-safe code
  - What is Synchronization?

Exercise for writing code with Synchronization

Given them a sample code and make it thread-safe by using Synchronization

- Resources:

  Functional Interface introduction

- Annotation
- Hibernate Validator - [Validation using Annotations](https://nareshkumarh.wordpress.com/2018/01/23/validation/)
- Log4J
- Reflection
  - [Reflection](https://nareshkumarh.wordpress.com/2016/03/01/reflection/)
- Concurrency
- Garbage Collection
- [Lombak](https://nareshkumarh.wordpress.com/2016/09/17/lombok-jar/) (Gets the repetitive tasks like getters, setters done; reduces lines of code)
- [Module-6 working with methods and encapsulation](https://nareshkumarh.wordpress.com/2016/03/24/module-6-working-with-methods-and-encapsulation/)
- Mockito JUnit
- Variable naming convention from Code Complete book

Certifications

- [JDK 17 Certification](https://catalog-education.oracle.com/pls/certview/sharebadge?id=6EEFFDDE0F96A660F5E7E359162CE8ED95385BDDD3B8EA391E487B1CC7094E5C)
- Try Enthuware subscription for JDK 17 Mock problems

### Solved 1:File I/O reading CSV

```java
package com.fssa.learnJava.corejava.day10;

import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.ArrayList;
import java.util.List;

/**
 * @author BharathwajSoundarara
 *
 */
public class FileReadIODemo {
	public static void main(String[] args) throws IOException {

		//Various methods to read a file
        System.out.println("-------1--------");
        Path path = Paths.get("C:\\code\\javaTeaching\\IOTest\\employees.txt");
        List<String> lines = Files.readAllLines(path);
        for (String line : lines) {
            System.out.println(line);
        }

        System.out.println("------2---------");
        List<String> lines2 = Files.readAllLines(path,StandardCharsets.UTF_8);
        StringBuilder sb = new StringBuilder();
        for (String line : lines2) {
            sb.append(line).append("\n");
        }
        System.out.println(sb);

        System.out.println("------3---------");
        byte[] bytes = Files.readAllBytes(path);
        String content  = new String(bytes);
        System.out.println(content);

        System.out.println("------Printing content organized way---------");

        List<String> lines4 = Files.readAllLines(path,StandardCharsets.UTF_8);
        ArrayList<String> arrLines = new ArrayList<String>(lines4);

        String headerLine = arrLines.get(0);

        String[] columns = headerLine.split(",");


        System.out.println(columns[0] + "|" + columns[1] +"|" + columns[2]);
       //TODO: Assignment to print the remaining of the lines as
        //Name:<NAME>
        //Title:
        //Salary

        //TODO: Find the average salary of employees
    }
}
```

Please use this page to add frequent errors that will be shared by students

- ClassNotFoundException during JDBC connection
- JUNIT library linking with maven
- Having issues while running a main method from eclipse
- Error with the PrepareStatement: PrepareStatement
- SQLException: Parameter index out of range (0 < 1)

  - Description: When the number of question marks in the PreparedStatement and number of parameters is not equal.

  ### Practice

  Question#1: Using the ArrayList<Integer> sort a list of integers read from the user

Sample Input:

_Enter numbers: 8 9 45 12 1_

Sample Output:

_Sorted list: 1 8 9 12 45_

Question#2: Read a list Task(id, name, deadlineDate) and print them in sorted order by deadline

use the below sample class

```java
class Task {
	private int id;
	private String name;
  private Date deadline;
}
```

Sample Input

3,Coding,20221022

5,Product Design,20221001

1,Software Design, 20221007

3,Coding,20221022

```java
Sample Output

5,Product Design,20221001

1,Software Design, 20221007

3,Coding,20221022

3,Coding,20221022
```

Question#3 (HOTS): Learn about Comparator and try implementing a logic where we take additional attribute for the Task called “priority” and if two tasks are pending on the same day, the sorting should be able to sort using both deadline and priority
