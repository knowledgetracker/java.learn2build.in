---
title: Day 7 - Set
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

- #### Task 1: Create Set , Set vs ArrayList (1)

```java

public class TestArrayListvsSet {

    public static void main(String[] args) {

        //ArrayList stores duplicates
        ArrayList<String> cityNames = new ArrayList<String>();
        cityNames.add("Delhi");
        cityNames.add("Chennai");
        cityNames.add("Chennai");
        cityNames.add("Bangalore");

        System.out.println("Using ArrayList :" + cityNames);

        //Set stores unique elements and ignores duplication
        HashSet<String> cityNamesSet = new HashSet<String>();
        cityNamesSet.add("Delhi");
        cityNamesSet.add("Chennai");
        cityNamesSet.add("Chennai");
        cityNamesSet.add("Bangalore");

        System.out.println("Using Set :" + cityNamesSet);


    }

}
```

- #### Task 2: TreeSet adding elements in Sorting order (1)

```java

import java.util.TreeSet;

public class TestTreeSet {

    public static void main(String[] args) {

        // TreeSet sorts the collections
        TreeSet<String> cityNames = new TreeSet<String>();
        cityNames.add("Delhi");
        cityNames.add("Chennai");
        cityNames.add("Bangalore");

        for (String cityName : cityNames) {
            System.out.println(cityName);
        }


    }

}
```

- #### Task 3 : Set Bulk operations (1)

Bulk operations are particularly well suited to Sets; when applied, they perform standard set-algebraic operations. Suppose s1 and s2 are sets. Here’s what bulk operations do:

- s1.containsAll(s2) — returns true if s2 is a subset of s1. (s2 is a subset of s1 if set s1 contains all of the elements in s2.)
- s1.addAll(s2) — transforms s1 into the union of s1 and s2. (The union of two sets is the set containing all of the elements contained in either set.)
- s1.retainAll(s2) — transforms s1 into the intersection of s1 and s2. (The intersection of two sets is the set containing only the elements common to both sets.)
- s1.removeAll(s2) — transforms s1 into the (asymmetric) set difference of s1 and s2. (For example, the set difference of s1 minus s2 is the set containing all of the elements found in s1 but not in s2.)

```java
package com.fssa.learnJava.corejava.day07;

import java.util.HashSet;
import java.util.Set;

public class SetBulkOperationsDemo {
	public static void main(String[] args) {

		Set<Integer> s1 = new HashSet<Integer> ();
		s1.add(1);
		s1.add(2);
		s1.add(3);
		s1.add(4);

		Set<Integer> s2 = new HashSet<Integer> ();
		s2.add(1);
		s2.add(2);
		s2.add(3);


		Set<Integer> union = new HashSet<Integer>(s1);
		union.addAll(s2);
		System.out.println(union);

		Set<Integer> intersection = new HashSet<Integer>(s1);
		intersection.retainAll(s2);
		System.out.println(intersection);

		Set<Integer> difference = new HashSet<Integer>(s1);
		difference.removeAll(s2);
		System.out.println(difference);

	}
}
```

- #### Task 4: Hashcode and Equals (1)

```java

  package com.fssa.learnJava.corejava.day07;

import java.util.ArrayList;
import java.util.HashSet;

/\*\*

- @author BharathwajSoundarara
- \*/

class Emp {

    int i;

    public Emp(int i) {
    	this.i = i;
    }

    @Override
    public int hashCode() {
    	final int prime = 31;
    	int result = 1;
    	result = prime * result + i;
    	return result;
    }

    @Override
    public boolean equals(Object obj) {
    	if (this == obj)
    		return true;
    	if (obj == null)
    		return false;
    	if (getClass() != obj.getClass())
    		return false;
    	Emp other = (Emp) obj;
    	if (i != other.i)
    		return false;
    	return true;
    }

}

public class HashCodeEqualsDemo {

    /**
     * @param args
     */
    public static void main(String[] args) {
    	// TODO Auto-generated method stub

        Emp emp1 = new Emp(23);
        Emp emp2 = new Emp(23);

        System.out.println("emp1.equals(emp2)--->>>" + emp1.hashCode());
        System.out.println("emp1.equals(emp2)--->>>" + emp2.hashCode());
        System.out.println("emp1.equals(emp2)--->>>" + emp1.equals(emp2));

        ArrayList<Emp> list = new ArrayList<Emp>();
        list.add(emp1);
        list.add(emp2);
        System.out.println("ArrayList size:" + list.size());

        HashSet<Emp> set = new HashSet<>();
        set.add(emp1);
        set.add(emp2);

        for (Emp emp : set) {
            System.out.println(emp);
        }

        System.out.println("HashSet size:" + set.size());

    }

}

```

### Practice

Question#1: Create an ArrayList of numbers with duplicate entries. Use an HashSet to remove the duplicates

Question#2: Create a ArrayList of Task with tasks having the same name and deadline. Use an HashSet to remove duplicate Task

```java
class Task {
	private int id;
	private String name;
	private Date deadline;

}
```
