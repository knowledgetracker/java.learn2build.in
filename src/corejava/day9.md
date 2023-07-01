---
title: Day 9 - Sorted
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

- #### Task 1: Sorting a list of strings demo

```java
package com.fssa.learnJava.corejava.day09;

import java.util.ArrayList;
import java.util.Collections;

public class CollectionSortingDemo {
	public static void main(String[] args) {
		ArrayList<String> cityNames = new ArrayList<String>();
		cityNames.add("Delhi");
		cityNames.add("Chennai");
		cityNames.add("Bangalore");

		System.out.println("Before Sort:" + cityNames);
		Collections.sort(cityNames);
		System.out.println("After Sort:" + cityNames);
	}
}
```

- #### Task : Sorting in reverse order and reverse functions in Collections

```java
package com.fssa.learnJava.corejava.day09;

import java.util.ArrayList;
import java.util.Collections;

public class SortingInReverseOrderDemo {
	public static void main(String[] args) {
		ArrayList<String> deptNames = new ArrayList<String>();
		deptNames.add("B");
		deptNames.add("D");
		deptNames.add("A");
		deptNames.add("C");

		System.out.println("Before Sorting: " + deptNames);
		Collections.sort(deptNames);
		System.out.println("After Sorting: " + deptNames);

		Collections.reverse(deptNames);
		System.out.println("Reverse:" + deptNames);



		ArrayList<String> deptNames2 = new ArrayList<String>();
		deptNames2.add("B");
		deptNames2.add("D");
		deptNames2.add("A");
		deptNames2.add("C");

		System.out.println("Before Sorting in reverse: " + deptNames);
		Collections.sort(deptNames2, Collections.reverseOrder());
		System.out.println("Reverse in reverse Order:" + deptNames2);
	}
}
```

- #### Task 3: Sorting by using Comparable Interface

```java
package com.fssa.learnJava.corejava.day09;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

class Account implements Comparable<Account> {

	private String accNo;
	private String name;
	private double balance;

	public Account(String accNo, String name, double balance) {

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
	public int compareTo(Account o) {

		if (balance == o.getBalance()) {
			return 0;
		} else {
			if (this.balance < o.getBalance()) {
				return 1;
			} else {
				return -1;
			}
			// return ( this.balance > o.getBalance()) ? 1: -1;
		}
	}

	@Override
	public String toString() {
		return "Account [accNo=" + accNo + ", name=" + name + ", balance=" + balance + "]";
	}

}

public class ComparableInterfaceDemo {
	public static void main(String[] args) {

		Account acct1 = new Account("A101", "Naresh", 1000);
		Account acct2 = new Account("A102", "Arun", 5000);
		Account acct3 = new Account("A103", "Karthik", 3000);

		List<Account> list = new ArrayList<Account>();
		list.add(acct1);
		list.add(acct2);
		list.add(acct3);

		System.out.println(list);

		Collections.sort(list);

		//Printing numbers sorted by balance
		System.out.println(list);

	}

}
```

### Additional Materials

- #### Making Collections ReadOnly

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class TestReadOnlyCollection {

    public static void main(String[] args) {

        List<String> cityNames = getAllCityNamesNew();
        System.out.println(cityNames);

        cityNames.add("Delhi");
        System.out.println(cityNames);

    }

    public static List<String> getAllCityNames() {
        List<String> cityNames = new ArrayList<String>();
        cityNames.add("Chennai");
        cityNames.add("Bangalore");
        return cityNames;
    }


    public static List<String> getAllCityNamesNew() {
        List<String> cityNames = new ArrayList<String>();
        cityNames.add("Chennai");
        cityNames.add("Bangalore");
        return Collections.unmodifiableList(cityNames);
    }

}
```

- #### Additional Example for Overriding hashCode and equals methods

```java
import java.util.Objects;

public class Movie {

   public int id;
   public String name;

   public Movie(int id, String name) {
       this.id = id;
       this.name = name;
   }

   @Override
   public int hashCode() {
       System.out.println("Going to calculate hash for this object: " + this);
       int hash = Objects.hash(id,name);
       System.out.println("HashCode:" + hash);
       return hash;
   }

   @Override
   public boolean equals(Object obj) {
       System.out.println("Going to do comparison - " + this + " vs " + obj );
       if (this == obj)
           return true;
       if (obj == null)
           return false;
       if (getClass() != obj.getClass())
           return false;
       Movie other = (Movie) obj;
       if (id != other.id)
           return false;
       if (name == null) {
           if (other.name != null)
               return false;
       } else if (!name.equals(other.name))
           return false;
       return true;
   }

   @Override
   public String toString() {
       return "Movie [id=" + id + ", name=" + name + "]";
   }


}
```

- #### Notes: List of Algorithms in Collections

  **List Algorithms:**

- sort — sorts a List using a merge sort algorithm, which provides a fast, stable sort. (A stable sort is one that does not reorder equal elements.)
- shuffle — randomly permutes the elements in a List.
- reverse — reverses the order of the elements in a List.
- rotate — rotates all the elements in a List by a specified distance.
- swap — swaps the elements at specified positions in a List.
- replaceAll — replaces all occurrences of one specified value with another.
- fill — overwrites every element in a List with the specified value.
- copy — copies the source List into the destination List.
- binarySearch — searches for an element in an ordered List using the binary search algorithm.
- indexOfSubList — returns the index of the first sublist of one List that is equal to another.
- lastIndexOfSubList — returns the index of the last sublist of one List that is equal to another.

### Pratice

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

Sample Output

```java

5,Product Design,20221001

1,Software Design, 20221007

3,Coding,20221022

3,Coding,20221022
```

Question#3 (HOTS): Learn about Comparator and try implementing a logic where we take additional attribute for the Task called “priority” and if two tasks are pending on the same day, the sorting should be able to sort using both deadline and priority
