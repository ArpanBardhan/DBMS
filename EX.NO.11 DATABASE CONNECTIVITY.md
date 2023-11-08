# Ex. No: 11 DATA BASE CONNECTIVITY USING  MYSQL AND JAVA
### DATE: 
### AIM: To create database connectivity and display the employee table 

### Steps:
1. Install mysql,visual studio,jdk, extensions of java pack.
2. Create a employee table and insert the data into employee table  
3. Create a new java project in visual studio.
4. write a java progarm to perform the following 1.create a connection 2. fetch data and store it in result set 3. Display table rows. 4. Close the connection
5. Deploy the jar file in lib folder 
6. Run the program

### Program:
```java
import java.sql.*;

public class App {
    public static void main(String args[]) {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/d1", "root",
                    "ForcaBarca@#10#11#09");
            // here sonoo is database name, root is username and password
            Statement stmt = con.createStatement();
            ResultSet rs = stmt.executeQuery("select * from employee");
            while (rs.next())
                System.out.println(rs.getInt(1) + "  " + rs.getString(2) + "  " + rs.getString(3));
            con.close();
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}

```
### Output:
![Screenshot 2023-11-08 170749](https://github.com/ArpanBardhan/DBMS/assets/119405037/fdb065da-fdaa-47f8-b40d-91810db7fded)


### Result:
Thust the database is connected and data displayed sucessfully.
