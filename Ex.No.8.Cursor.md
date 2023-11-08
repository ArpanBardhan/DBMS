# Ex. No: 8 PL/SQL program using Cursor 
### DATE: 07/11/2023
### AIM: To create PL/SQL program to display the customer table 

### Steps:
1. Declare the variable  in Declare section.
2. Fetch the variable with datatype similar to data type in cursor 
3. Create a cursor to select all rows from customers table.
4. Display the result 
5. End the begin section.

### Program:
### CREATE EMPLOYEE TABLE:
```
CREATE TABLE employd (
  empid NUMBER,
  empname VARCHAR(10),
  dept VARCHAR(10),
  salary NUMBER
);
select * from employd;
INSERT INTO employd VALUES (1, 'Nagul', 'Sales', 100000);
INSERT INTO employd VALUES (2, 'Arvind', 'Marketing', 120000);
```
### PLSQL Cursor code
```
DECLARE
   CURSOR employd_cursor IS
   SELECT empid,empname,dept,salary
   FROM employd;
   emp_id NUMBER;
   emp_name VARCHAR(50);
   emp_dept VARCHAR(50);
   emp_salary NUMBER;
BEGIN
  OPEN employd_cursor;

  LOOP
    FETCH employd_cursor INTO emp_id, emp_name, emp_dept, emp_salary;

    EXIT WHEN employd_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
    DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
  END LOOP;

  CLOSE employd_cursor;
END;

```


### Output:
![270953105-ce695c15-61e5-49f0-9d97-6687e007db95](https://github.com/vinodkumar-s/DBMS/assets/113497226/2faf5781-f797-423b-a749-6dd436692eeb)


### Result:
Thust the program was performed sucessfully.
