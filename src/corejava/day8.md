---
title: Day 8 - Map
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

- #### Task 1: Creating a hashmap using collections library

```java


package com.fssa.learnJava.corejava.day08;

import java.util.HashMap;

/**
 * @author BharathwajSoundarara
 *
 */
public class HashMapDemo {
	public static void main(String[] args) {

		// Task: store department name and no of employees working in the department
		HashMap<String, Integer> marksMap = new HashMap<String, Integer>();
		marksMap.put("HR", 5);
		marksMap.put("ADMIN", 10);
		marksMap.put("DEVELOPERS", 300);

		// Iterate
		for (String deptName : marksMap.keySet()) {

			Integer count = marksMap.get(deptName);
			System.out.println("Department Name:" + deptName + " and Employee Count :" + count);

		}

	}

}
```

- #### Task 2: Modifying a HashMap (1)

```java
package com.fssa.learnJava.corejava.day08;

import java.util.HashMap;

public class ModifyingAHashMapDemo {
	public static void main(String[] args) {

		// Task: store department name and no of employees working in the department
		HashMap<String, Integer> marksMap = new HashMap<String, Integer>();
		marksMap.put("HR", 5);
		marksMap.put("ADMIN", 10);
		marksMap.put("DEVELOPERS", 300);


		// Modifying a particular count
		int hrCount = marksMap.get("HR");
		hrCount += 1;
		marksMap.put("HR", hrCount);

		// Iterate
		for (String deptName : marksMap.keySet()) {

			Integer count = marksMap.get(deptName);
			System.out.println("Department Name:" + deptName + " and Employee Count :" + count);

		}
	}
}
```

### Practice

Question#1: Read comma separated list of names from the user and print count

Sample Input

Enter the string: Ram, Ram, Superman, spider, hey, hello, hey, Spider

```java
Output

Ram: 2

Superman: 1

Spider: 2

hey: 2

hello: 1
```

Question#2: Write code to read a comma separated DeptName, EmployeeName and output DeptName, List of Employees

Sample Input

HR,Ram

HR, Suresh

IT, Basker

IT, Joseph

Admin, Sundar

```java
Output

HR: Ram, Suresh

IT: Basker, Joseph

Admin: Sundar
```

Question#3 (HOTS): Implement your own HashMap
