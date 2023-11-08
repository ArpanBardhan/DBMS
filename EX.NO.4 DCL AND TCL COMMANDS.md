# EX.NO 4 Data Control Language (DCL) Commands and Transaction Control Languages (TCL) in SQL
### DATE:07/11/2023
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## Data Control Language (DCL) commands
* Data control language (DCL) is used to access the stored data.
* It is mainly used for revoke and to grant the user the required access to a database.
## List of DCL commands: 
1. GRANT : It is used to insert data into a table.
2. REVOKE: It is used to update existing data within a table.
## Transaction control language(TCL) commands
1. COMMIT : COMMIT command in SQL is used to save all the transaction-related changes permanently to the disk
2. START TRANSACTION : to start the transaction
3. ROLLBACK : undo the transaction upto savepoint 
4. SAVEPOINT : create a savepoint to save the different parts of the same transaction using different names

### Q1) Create a table employee with employee id ,name and Address

### QUERY:
```sql
sql
create table employee(
emp_id numeric,
emp_name varchar(10),
addr varchar(40)
);
```

### OUTPUT:
![image](https://github.com/NITHISH74/DBMS/assets/94164665/c4cab10d-4e7b-43e3-bd27-0c1b05d72a51)

### Q2) Insert three rows into emploee table 
### QUERY:
```sql
sql
insert into employee values(1,'Luffy','EastBlue');
insert into employee values(2,'Shanks','GodValley');
insert into employee values(3,'Grap','MarinFord');
```

### OUTPUT:
![image](https://github.com/NITHISH74/DBMS/assets/94164665/cc54e921-a030-414c-a435-5acef8af12bb)

### Q3) Start the transaction and create a save point s1.

### QUERY:
```sql
sql
savepoint A;
```

### OUTPUT:
![image](https://github.com/NITHISH74/DBMS/assets/94164665/49e6e831-20fe-4bf8-b56e-1e333fa6c3c3)

### Q4) Perform insertion into employee table.

### QUERY:
```sql
sql
insert into employee(4,'Robin','EniesLobby');
```

### OUTPUT:
![image](https://github.com/NITHISH74/DBMS/assets/94164665/1277f006-3a41-46f9-8ad1-08e874ec3b1a)


### Q5)	Display the employee table and create a save point s2 .
### QUERY:

```sql
sql
select * from employee;
savepoint s2;
```



### OUTPUT:
![image](https://github.com/NITHISH74/DBMS/assets/94164665/e7fca0ef-23d6-4a2a-b02c-aa865032db75)


### Q6)	Perform updation on any one of the row.
### QUERY:
```sql
sql
update employee set emp_name='Nico Robin' where emp_id=4;
```

### OUTPUT:
![image](https://github.com/NITHISH74/DBMS/assets/94164665/50e2ef49-513c-43ad-ad2a-c4971fd0fc7a)


### Q7) Display the employee table and rollback to  save point s2 
### QUERY:
```sql
sql
select * from employee;
rollback to s2;

```

### OUTPUT:
![image](https://github.com/NITHISH74/DBMS/assets/94164665/f9b6fbb2-a118-4360-a7d2-3fa4f6d85a25)


### Q8) Display the employee table and commit the changes; 
### QUERY:
```sql
sql
select * from employee;
commit;
```

### OUTPUT:
![image](https://github.com/NITHISH74/DBMS/assets/94164665/f64c5b14-4d95-4a9d-95a3-1322d3bd9eea)


### Q9) Rollback to save point s1;
### QUERY:
```sql
sql
rollback to A;
```

### OUTPUT:
![image](https://github.com/NITHISH74/DBMS/assets/94164665/82262c70-5160-4625-b724-cd3c4370d07e)




## RESULT :
Thus the basic TCL and DCL commands are executed.
