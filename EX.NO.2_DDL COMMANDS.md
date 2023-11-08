# EXP NO 2: DATA DEFINITION LANGUGE COMMANDS 
### DATE
## AIM:
To create a student database and execute DDL queries using SQL.


## THEORY
### DDL (Data Definition Language)

* DDL or Data Definition Language actually consists of the SQL commands that can be used to define the database schema.
* It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects in the database.
* DDL is a set of SQL commands used to create, modify, and delete database structures but not data.
* These commands are normally not used by a general user, who should be accessing the database via an application.

 
### List of DDL commands: 
1. CREATE: This command is used to create the database or its objects (like table, index, function, views, store procedure, and triggers).
2. DROP: This command is used to delete objects from the database.
3. ALTER: This is used to alter the structure of the database.
4. TRUNCATE: This is used to remove all records from a table, including all spaces allocated for the records are removed.
5. RENAME: This is used to rename an object existing in the database.

## Query:
### 1) Create a database studentdb

### SQL QUERY:
```
Create a database studentdb;
```
### OUTPUT:
![Screenshot 2023-11-08 134816](https://github.com/ArpanBardhan/DBMS/assets/119405037/67c7b621-4f7a-4e8b-b315-f2e1eec02587)

### 2) Create a table student  and insert any two rows with the following fieds RegisterNumber,Name,Age,Address,Phone number

### SQL QUERY: 
```
create table student(RegisterNo int,Name char(20),age int,Address varchar(20),PhoneNo int);
```
### OUTPUT:
![Screenshot 2023-11-08 135117](https://github.com/ArpanBardhan/DBMS/assets/119405037/b2e74280-3827-4f17-8c7e-ead25b35138f)
![Screenshot 2023-11-08 135302](https://github.com/ArpanBardhan/DBMS/assets/119405037/f8be0cd9-67ab-4820-9c2d-589bd705bf3f)

### 3) Alter the above student table by adding another attribute department

### SQL QUERY: 
```
alter table student add Department char(30);
```
### OUTPUT:
![Screenshot 2023-11-08 135431](https://github.com/ArpanBardhan/DBMS/assets/119405037/65bd2975-fbba-4c09-ba92-6fae7b3ca872)

### 4) Rename the student table to mystudent

### SQL QUERY: 
```
alter table student rename to mystudent;
```
### OUTPUT:
![Screenshot 2023-11-08 140005](https://github.com/ArpanBardhan/DBMS/assets/119405037/217966fc-db33-4349-9f26-8f3fca616f99)

### 5) Delete the mystudent rows using truncate keyword

### SQL QUERY: 
```
truncate table student;
```
### OUTPUT:
![Screenshot 2023-11-08 140659](https://github.com/ArpanBardhan/DBMS/assets/119405037/2489a45b-434e-492b-bbc3-a7fca489624a)

### 4) Drop the mystudent table

### SQL QUERY: 
 ```
drop table student;
```
### OUTPUT:
![Screenshot 2023-11-08 135518](https://github.com/ArpanBardhan/DBMS/assets/119405037/af09c697-4418-48a6-a6eb-d5f2f5172654)









## Result:
         Thus the basic DDL commands in SQL are executed. 


