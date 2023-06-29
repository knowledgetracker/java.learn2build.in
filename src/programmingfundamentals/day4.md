---
title: Day 04 - Class and Methods
description: 
date: 2023-06-06
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
  package day04;

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
  // Filename: User.java

  public class User {

      String name;
      String email;
      String password;
      long phoneNo;

      public String getName(){
          return name;
      }

      public void setName(String newName){
          name = newName;
      }
    
        public String getEmail(){
          return email;
      }

      public void setEmail(String newEmail){
          email = newEmail;
      }

      public long getPhoneNo(){
          return phoneNo;
      }

      public void setPhoneNo(long newPhoneNo){
          phoneNo = newPhoneNo;
      }

      public long getPassword(){
          return password;
      }

      public void setPassword(String newPassword){
          password = newPassword;
      }

      @Override
        public String toString() {
          String userDetails = "{ name: "+name+" email: "+email+" phoneNo: "+phoneNo+" }";
          System.out.println(userDetails);
          return userDetails;
        }
      
  }



  // Filename App.java

  public class App {
    
      public static void main(String[] args){
          
          User user1 = new User();
          user1.setName("Surya");
          user1.setEmail("surya@gmail.com");
          user1.setPhoneNo(9876543210L);
          user1.setPassword("supersecretpassword");
          
          user1.toString();

          User user2 = new User();
          user2.setName("Vijay");
          user2.setEmail("vijay@gmail.com");
          user2.setPhoneNo(9876543210L);
          user2.setPassword("highlysecurepassword");
          
          user1.toString();
          
      }

  }

```


### Practice

```
- Creating a 'Student' class with methods to set and get the student details.
- Creating a 'Calculator' class that performs various mathematical operations.  (Addition, Sub, Multiplication & Division)
```


