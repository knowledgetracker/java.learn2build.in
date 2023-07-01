---
title: Day 12 -  JDBC Querying
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

- #### Task 1: Insert Query

```java
/**
*
*/
package com.fssa.learnJava.corejava.day14;

import com.fssa.learnJava.corejava.day13.ConnectionUtil;

import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.Statement;

/**
* @author BharathwajSoundarara
*
*/

public class UserQuery {

   public static void main(String[] args) throws Exception {


       Connection connection = ConnectionUtil.getConnection();
       System.out.println(connection);

       Statement stmt = connection.createStatement();

       // Step 03: Execute Insert Query
       String query ="INSERT INTO USERS (user_name, email_id, additional_info, password) VALUES (\"vinit_gore\",\"vinit.gore@ctr.freshworks.com\",\"Instructor FSSA\", \"password007\")";
       int rows = stmt.executeUpdate(query);
       System.out.println("No of rows inserted :" + rows );

       //Step 04: Execute SELECT Query
       final String selectQuery = "SELECT user_id,user_name,email_id,additional_info FROM USERS";

       //Step 05: Get the resultset
       ResultSet rs = stmt.executeQuery(selectQuery);

       //Step 06: Iterate the result
       while ( rs.next()) {
       	int userId = rs.getInt("user_id");
       	String userName = rs.getString("user_name");
           String emailID = rs.getString("email_id");

           System.out.println("UserId:" + userId +", UserName:" + userName + ", EMAIL ID:" + emailID);
       }

       //Step 07: close the connection resources
       rs.close();
       stmt.close();
       connection.close();



   }

}
```

- #### Task 2:

```java
package com.fssa.learnJava.corejava.day14;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.ResultSet;

import com.fssa.learnJava.corejava.day13.ConnectionUtil;

/**
 * @author BharathwajSoundarara
 *
 */
//Explain in class what is the difference between Statement and PreparedStatement
public class UserQueryPrepStmt {
	public static void main(String[] args) throws Exception{
		Connection connection = ConnectionUtil.getConnection();
		String query ="INSERT INTO USERS (user_name, email_id, additional_info, password) VALUES ( ?, ?, ? ,? );";
		PreparedStatement pst = connection.prepareStatement(query);
		pst.setString(1, "bharathwaj");
		pst.setString(2, "bharathwaj.soundararajan@ctr.freshworks.com");
		pst.setString(3, "Coach");
		pst.setString(4, "password007");
		System.out.println(pst.toString());
		int rows2 = pst.executeUpdate();
		System.out.println("No of rows inserted :" + rows2 );
		pst.close();

	}

}
```

- #### Task 3: Update Query JDBC

```java
  package com.fssa.learnJava.corejava.day14;

import java.sql.Connection;
import java.sql.PreparedStatement;

import com.fssa.learnJava.corejava.day13.ConnectionUtil;

/\*\*

- @author BharathwajSoundarara
- _/
  public class TestUserUpdatePassword {
  public static void main(String[] args) throws Exception {
  Connection connection = ConnectionUtil.getConnection();
  // Input
  String userName = "bharathwaj";
  String password = "mypassword_(";


   // DEPOSIT
  String query = "UPDATE users SET password=? WHERE user_name=?";
  PreparedStatement pst = connection.prepareStatement(query);
  pst.setString(1, password);
  pst.setString(2, userName);
  int rows = pst.executeUpdate();
  System.out.println("No of rows updated" + rows);
  }

}

```

### Resources

Resources Link 1:[Statement vs PreparedStatement](https://nareshkumarh.wordpress.com/2015/06/11/task-2-statement-vs-preparedstatement/)

Resources Link 2:[update Query](https://nareshkumarh.wordpress.com/2015/06/11/task-05-deposit-amount-in-account-update-query/)

Assignment:

Redo the above examples for table specific to your project

Resources Enum Optional topic

- [Movieapp ticketstatus using enum](https://nareshkumarh.wordpress.com/2018/01/17/movieapp-ticketstatus-using-enum/)
- [Movie app ticket status without enum](https://nareshkumarh.wordpress.com/2018/01/17/movieapp-ticket-status-without-enum/)
