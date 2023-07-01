---
title: Day 6 - ArrayList
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

- #### Task 1: Create an ArrayList and store city names

Snippet 1 : Store city names in a ArrayList

```java
import java.util.ArrayList;

public class TestArrayList {

    //without using generics
    public static void main(String[] args) {

        // Store the city names in the List
        ArrayList cityList  = new ArrayList();
        cityList.add("Chennai");
        cityList.add("Bangalore");
        cityList.add("Mumbai");

        // Display the city names
        for (Object object : cityList) {
            String cityName = (String) object; // TypeCast object to String
            System.out.println(cityName);
        }

    }

}
```

Snippet 2: Store city names using Generics

```java
import java.util.ArrayList;

public class TestArrayListWithGenerics {

    public static void main(String[] args) {

        // Store the city names in the List ( use Generics )
        ArrayList<String> cityList  = new ArrayList<String>();
        cityList.add("Chennai");
        cityList.add("Bangalore");
        cityList.add("Mumbai");

        // Display the city names
        for (String cityName : cityList) {
            System.out.println(cityName);
        }

    }

}
```

Snippet 1:

- The first snippet demonstrates the usage of `ArrayList` **without generic type**.
- The `ArrayList` is declared without specifying the type of elements it will hold, allowing any type of object to be added.
- The elements are retrieved using the `for-each` loop, and a **typecast** `(String)` is required to convert the retrieved object to a String.

Snippet 2:

- The second snippet showcases the usage of `ArrayList` **with generic type**.
- The `ArrayList` is declared with the type parameter `<String>`, indicating that it can only store `String` objects.
- The elements are retrieved using the `for-each` loop directly as `String` objects, eliminating the need for typecasting.

Difference:

- The main difference between the two snippets is the use of **generic type** in the second snippet.

```java

💡 **Generic type:**

- Using generic types provides type safety by enforcing the type of elements stored in the `ArrayList` at compile-time.
- It eliminates the need for explicit typecasting when retrieving elements, resulting in cleaner and safer code.

```

- #### Task 2: Convert Arrays to List

```java
String[] deptNames = new String[3];
deptNames[0] = "CSE";
deptNames[1] = "EEE";
deptNames[2] = "MECH";
List<String> list = Arrays.asList(deptNames);
System.out.println(list);
```

- #### Task 3: Collections shuffle

The **Collections.shuffle** method is used to randomly shuffle the elements in a collection.

```java
public class Shuffle {
    public static void main(String[] args) {
        List<String> list = Arrays.asList(args);
        Collections.shuffle(list);
        System.out.println(list);
    }
}
```

- #### Task 4: Collections frequency
  The **Collection.frequency** method in Java is used to count the number of occurrences of a specified element in a collection.

```java
Collection<String> list = new ArrayList<>();
list.add("cse");
list.add("cse");
list.add("eee");
int cnt = Collections.frequency(list, "cse");
System.out.println(cnt);
```

### Practice

Question#1: Create a array of objects of Tasks.

Task Object

```java
public class Task {

    public String taskName;

    public String assignedTo;

    public int priority;


}
```

Question#2: Add logic to remove duplicate tasks from the array without using Set or any inbuilt collection

Question#3: Find an task in the ArrayList with taskName “Testing”
