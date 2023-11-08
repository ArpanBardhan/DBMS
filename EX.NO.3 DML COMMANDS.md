# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## DML(Data Manipulation Language)
*  The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements.
*  It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands: 
1. INSERT: It is used to insert data into a table.
2. UPDATE: It is used to update existing data within a table.
3. DELETE: It is used to delete records from a database table.
4. SELECT: The SELECT command shows the records of the specified table.

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);

```
### OUTPUT:
![Screenshot 2023-11-08 143528](https://github.com/ArpanBardhan/DBMS/assets/119405037/548c3b90-cb7e-473f-9290-9eba4d6edbca)

### Q2) Delete the records from manager table where the salary less than 2750.
```
delete from manager where salary<2750;
```
### QUERY:

### OUTPUT:
![Screenshot 2023-11-08 143540](https://github.com/ArpanBardhan/DBMS/assets/119405037/c23b6db8-abe2-4dea-b276-19773c250bc3)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![Screenshot 2023-11-08 143549](https://github.com/ArpanBardhan/DBMS/assets/119405037/34965163-f356-40a0-be1f-04cb3fc6f5e8)

### Q5)	List the names of Clerks from emp table.


### QUERY:
```
select ename from manager where designation='clerk';
```

### OUTPUT:
![Screenshot 2023-11-08 143601](https://github.com/ArpanBardhan/DBMS/assets/119405037/25a686e1-172f-4963-9931-932127f86e77)


### Q6)	List the names of employee who are not Managers.


### QUERY:
```
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![Screenshot 2023-11-08 143613](https://github.com/ArpanBardhan/DBMS/assets/119405037/9a6ed8d1-d45a-438b-80e5-49e0482dbc0f)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from manager where commission=0;
```

### OUTPUT:
![Screenshot 2023-11-08 143624](https://github.com/ArpanBardhan/DBMS/assets/119405037/e45bedca-a09b-4eeb-909c-42617f0533d5)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![Screenshot 2023-11-08 143636](https://github.com/ArpanBardhan/DBMS/assets/119405037/eead5554-2b3b-4884-be4b-1ae99ff1fecd)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:

```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![Screenshot 2023-11-08 143647](https://github.com/ArpanBardhan/DBMS/assets/119405037/116ccf91-2738-46cb-9ce5-b266f6bd80b4)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from manager where hiredate<str_to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![Screenshot 2023-11-08 144710](https://github.com/ArpanBardhan/DBMS/assets/119405037/67927b54-02e8-43c5-bd30-606e8cb01787)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![Screenshot 2023-11-08 143708](https://github.com/ArpanBardhan/DBMS/assets/119405037/5cb30712-d71d-434e-ab43-6bca501255ac)


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![Screenshot 2023-11-08 143718](https://github.com/ArpanBardhan/DBMS/assets/119405037/a1b9a4b4-5489-4567-9a3d-c4f28bea1318)

### Q13) Find number of rows in the table EMP

### QUERY:
```
 select count(*) from manager;
```

### OUTPUT:
![Screenshot 2023-11-08 143725](https://github.com/ArpanBardhan/DBMS/assets/119405037/9f1e061d-9142-40df-966b-cd17c1da528a)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select max(salary) as MAX,min(salary) as MIN, avg(salary) as AVG from manager;
```

### OUTPUT:
![Screenshot 2023-11-08 144251](https://github.com/ArpanBardhan/DBMS/assets/119405037/7c3495d4-9008-4667-b681-653e498f354f)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![Screenshot 2023-11-08 143807](https://github.com/ArpanBardhan/DBMS/assets/119405037/90cb1178-7596-4c20-a6e8-8f93a4d8bc1b)


## RESULT :
Thus the basic DML commands are executed.
