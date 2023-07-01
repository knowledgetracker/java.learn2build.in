---
title: Day 3 - Constructors
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

- #### Task 1: Create a Bank Account

Create a class **Account** :

```java
class Account2 {

	private String accNo;

	private String name;

	private double balance;

	// Default Constructor
	public Account2() {

	}

	// Creating a Constructor which accepts all the attributes: Constructor
	// Overloading
	public Account2(String accNo, String name, double balance) {
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
		return balance;Testing:



	}

	public void setBalance(double balance) {
		this.balance = balance;
	}

}
```

Testing:

```java
public class TestAccount2 {
	public static void main(String[] args) {

		// create Account using Setter methods and Default constructor
		Account2 acct1 = new Account2();
		acct1.setAccNo("A101");
		acct1.setName("Naresh");
		acct1.setBalance(1000);

		System.out.println(acct1.getAccNo() + "-" + acct1.getName() + "-"
				+ acct1.getBalance());

		// Create Account with Overloaded constructor accepting parameters
		Account2 acct2 = new Account2("A102", "Arun", 1000);
		System.out.println(acct2.getAccNo() + "-" + acct2.getName() + "-"
				+ acct2.getBalance());

	}
}
```

- #### Task 3: Create a Constructor and initialize values

```java
public class Account {

    public String accNo;

    public String name;

    public double balance;


    public Account(String accNo, String name, double balance) {
        this.accNo = accNo;
        this.name = name;
        this.balance = balance;
    }


}
```

Testing:

```java
public class TestAccount {

    public static void main(String[] args) {

        //create Account
        Account acct1 = new Account("A101", "Naresh" , 1000 );
        System.out.println(acct1.accNo + "-" + acct1.name + "-" + acct1.balance);


        //create Account
        Account acct2 = new Account("A102","Arun", 1000);
        System.out.println(acct2.accNo + "-" + acct2.name + "-" + acct2.balance);
    }

}
```

### Practice

Question 1: Edit the code below to get the following expected output:

```java
public class Employee {

    private int id;
    private String name;

    public Employee(int id, String name) {
        this.id = id;
        this.name = name;
    }
}
```

```java
package day03_constructors

public class TestEmployee {

    public static void main(String[] args) {
        Employee e1 = new Employee(1, "naresh");
        Employee e2 = new Employee(2, "suresh");
    }
}
```

Expected output:

```java


id=1, name=naresh

id=2, name=suresh
```

Question 2: Create a User class with 2 constructors. the second overloaded constructor User(name, password, emailId)
