# Ex. No: 9 PL/SQL program using Triggers 
### DATE: 07/11/2023
### AIM: To create PL/SQL program to display new and old salary of customer when before/ after updation takes place. 

### Steps:
1. Create a trigger for each row when updation occurs.
2. Declare the variable in Declare section.
3. Start the begin section.
4. Calculate the salary changes.
5. Display the result 
6. End the begin section.

### Program:
```
CREATE TABLE employed(
  empid NUMBER,
  empname VARCHAR2(10),
  dept VARCHAR2(10),
  salary NUMBER
);

CREATE TABLE sal_log (
  log_id NUMBER GENERATED ALWAYS AS IDENTITY,
  empid NUMBER,
  empname VARCHAR2(10),
  old_salary NUMBER,
  new_salary NUMBER,
  update_date DATE
);
-- Insert the values in the employee table
insert into employed values(1,'Nagul','AIDS',1000000);
insert into employed values(2,'Santhosh','CSE',500000)
```
### Create employee table

![270734960-ab8e1001-ad81-4cee-b147-9e6ccbffe6b7](https://github.com/vinodkumar-s/DBMS/assets/113497226/9ee3cc5f-8053-408a-ac14-1936fd4341ae)

### Create salary_log table

![270735026-86466cf5-53f7-4063-9ccc-e364e7072d5e](https://github.com/vinodkumar-s/DBMS/assets/113497226/130a90ee-f128-4682-8362-76c2c94172c8)


### PLSQL Trigger code
```
-- Create the trigger
CREATE OR REPLACE TRIGGER log_sal_update
BEFORE UPDATE ON employed
FOR EACH ROW
BEGIN
  IF :OLD.salary != :NEW.salary THEN
    INSERT INTO sal_log (empid, empname, old_salary, new_salary, update_date)
    VALUES (:OLD.empid, :OLD.empname, :OLD.salary, :NEW.salary, SYSDATE);
  END IF;
END;
/
-- Insert the values in the employee table
insert into employed values(1,'Nagul','AIDS',1000000);
insert into employed values(2,'Santhosh','SALES',500000);

-- Update the salary of an employee
UPDATE employed
SET salary = 60000
WHERE empid = 1;
-- Display the employee table
SELECT * FROM employed;

-- Display the salary_log table
SELECT * FROM sal_log;
```
### Output:
![270736789-98d6405f-b231-485b-b7c5-38e605977906](https://github.com/vinodkumar-s/DBMS/assets/113497226/3ba9322a-cf96-42f9-8879-90eed3cafbf4)

![270947264-789b4d02-718d-4f9c-b4e3-defb7a76c0ef](https://github.com/vinodkumar-s/DBMS/assets/113497226/ee086f7e-2c85-4b00-9ced-1cd94ff7d49b)

### Result:
Thust the program was performed sucessfully.
