# EXP NO 10: SYNONYMS AND ASSERTIONS IN SQL 
### DATE: 07/11/2023
## AIM:
To create a student database and create a synonym and assertions.

## THEORY
## SYNONYM
<div align="justify">
A SYNONYM provides another name for database object, referred to as original object, that may exist on a local or another server.
</div>

## ASSERTIONS
<div align="justify">
* An assertion is a piece of SQL which makes sure a condition is satisfied, else or it stops the action being taken on a database.
* An assertion is a constraint that might be dependent upon multiple rows of multiple tables.
</div>

## Query:
### 1) Create a table EMPLOYEE and perform insertion of two rows.

### SQL QUERY: 
```
CREATE TABLE EMPLOYEE (
    employee_id INT ,
    name VARCHAR(255),
    department VARCHAR(255),
    salary DECIMAL(10, 2)
);
```


### OUTPUT:
![Screenshot 2023-10-21 190258](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/71b5a740-3ed6-400c-a81e-55b48f5a29f8)
![Screenshot 2023-10-21 190547](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/f4d76026-48c5-4d61-a806-4befa6e93d93)





### 2) Create a synonym S1 for EMPLOYEE  table.

### SQL QUERY: 
```
CREATE SYNONYM S1 FOR EMPLOYEE;
```

### OUTPUT:
![Screenshot 2023-10-21 190453](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/b455ceaa-8657-442e-b801-a7c7b7e87b67)




### 3) Display the EMPLOYEE  table using synonym S1.
 
### SQL QUERY: 
```
SELECT * FROM S1;
```


### OUTPUT:

![Screenshot 2023-10-21 190740](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/6919a5b8-9f79-4180-a956-3df97ee88b03)




### 4) Drop the synonym.

### SQL QUERY: 
```
DROP SYNONYM S1;
```


### OUTPUT:

![Screenshot 2023-10-21 190827](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/6368462e-e8b5-4451-8364-19a41290c302)


### 5) Create a supplier table and create a sequence S2 for supplier table id.

### SQL QUERY: 
```
CREATE TABLE supplier (
    id INT,
    name VARCHAR(255),
    address VARCHAR(255),
    contact_person VARCHAR(255)
);

CREATE SEQUENCE S2 START 1;

```


### OUTPUT:

![Screenshot 2023-10-21 190838](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/6941eec5-a29d-49f2-b642-9faa553c5710)

![Screenshot 2023-10-21 190934](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/4fd3c19f-6eb2-433a-b260-cb701ca8daac)


### 6) insert the data into supplier table use sequence.

### SQL QUERY: 
```
INSERT INTO supplier (id, name, address, contact_person)
VALUES (NEXTVAL('S2'), 'ABC Suppliers', '123 Main Street', 'John Doe');

INSERT INTO supplier (id, name, address, contact_person)
VALUES (NEXTVAL('S2'), 'XYZ Distributors', '456 Elm Road', 'Jane Smith');
```


### OUTPUT:

![Screenshot 2023-10-21 191122](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/2f779d72-49da-4e24-8749-575d5625a31b)


### 7) Drop the sequence

### SQL QUERY: 
```
DROP SEQUENCE S2;
```


### OUTPUT:

![Screenshot 2023-10-21 191127](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/bde530b6-caf5-48e6-96a6-e32d87846e74)



## RESULT :
### Thus the sequence and synonym created and used in SQL.
