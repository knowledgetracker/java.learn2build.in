---
title: Day 11 - JDBC
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

- #### Task 1:JDBC MySQL Test Connection

```java
/**
 *
 */
package com.fssa.learnJava.corejava.day13;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

/**
 * @author BharathwajSoundarara
 *
 */
public class TestMysqlConnectionDemo {
	/**
	 * @param args
	 */

	public static void main(String[] args) throws ClassNotFoundException, SQLException {
		Class.forName("com.mysql.cj.jdbc.Driver");
		Connection conn = DriverManager.
														getConnection("jdbc:mysql://localhost:3306/<YOURDB>",
																					"USERNAME",
																					"PASSWORD");
		System.out.println(conn);

	}
}
```

- #### Task 2: JDBC Connection Refactoring MySQL

```java
  package com.fssa.learnJava.corejava.day13;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class ResuableTestConnection {

    public static void main(String[] args) throws SQLException {

        Connection connection = ResuableTestConnection.getConnection();
        System.out.println(connection);

    }

    public static Connection getConnection() {

        Connection connection  = null;
        try
        {
            Class.forName("com.mysql.cj.jdbc.Driver");

             String url = "jdbc:mysql://localhost:3306/YOURDB";
             connection = DriverManager.getConnection(url,"USERNAME", "PASSWORD");

        } catch (Exception e) {
            e.printStackTrace();
        }
        return connection;
    }

}

```

- #### Task 3: JDBC Connection and Close Connection Util class

```java
package com.fssa.learnJava.corejava.day13;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class ConnectionUtil {

    public static Connection getConnection() throws Exception {

        Connection con = null;
        String url = "jdbc:mysql://localhost/YOURDB";
        String userName = "USERNAME";
        String passWord = "PASSWORD";
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            con = DriverManager.getConnection(url, userName, passWord);
        } catch (Exception e) {
            e.printStackTrace();
            throw new Exception(e);
        }
        return con;
    }

    public static void close(Connection conn , Statement stmt, ResultSet rs){

        try
        {
            if ( rs != null ){
                rs.close();
            }
            if ( stmt != null ) {
                stmt.close();
            }
            if ( conn != null ){
                conn.close();
            }
        }
        catch(SQLException e){

        }
    }
}
```

```java
 Dependency
 <dependency>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
			<version>8.0.33</version>
</dependency>
```

Assignments:

Redo the solved examples for the database setup in your Dev environment
