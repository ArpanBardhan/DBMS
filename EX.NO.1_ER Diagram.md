# EXP NO 1: ER DIAGRAM CREATION, RELATIONAL MODEL AND SCHEMA GENERATION  
### DATE
## AIM:
<div align="justify">
   To create a ER Diagram for Bank management system or College management system using ERD Plus tool and generate the relational model with schema. 
</div>

## Algorithm
1. Create a login with https://erdplus.com.
2. Create a new ER Diagram with name
3. Create a strong entity, relation and attributes.
4. Create a weak entity, relation and attributes.
5. Specify attributes unique, multivalued and composite attributes.

### ER Diagram 
![image (6)](https://github.com/ArpanBardhan/DBMS/assets/119405037/87c91cff-549e-4f9b-852c-cdca05e2d472)


### Relational model
![image (7)](https://github.com/ArpanBardhan/DBMS/assets/119405037/e18e92b0-911b-4ffc-9bf9-050dea5bd13a)


### SQL DDL Schema 
```SQL
CREATE TABLE CUSTOMER
(
  CUST_ID INT NOT NULL,
  FIRST_NAME INT NOT NULL,
  LAST_NAME INT NOT NULL,
  PHONE INT NOT NULL,
  ADDRESS INT NOT NULL,
  PRIMARY KEY (CUST_ID)
);

CREATE TABLE LOAN
(
  LOAN_ID INT NOT NULL,
  LOAN_TYPE INT NOT NULL,
  AMOUNT INT NOT NULL,
  PRIMARY KEY (LOAN_ID)
);

CREATE TABLE BANK
(
  NAME INT NOT NULL,
  CODE INT NOT NULL,
  ADDRESS INT NOT NULL,
  PRIMARY KEY (CODE)
);

CREATE TABLE BRANCH
(
  BRANCH_ID INT NOT NULL,
  NAME INT NOT NULL,
  ADDRESS INT NOT NULL,
  LOAN_ID INT NOT NULL,
  PRIMARY KEY (BRANCH_ID),
  FOREIGN KEY (LOAN_ID) REFERENCES LOAN(LOAN_ID)
);

CREATE TABLE AVAILED_BY
(
  LOAN_ID INT NOT NULL,
  CUST_ID INT NOT NULL,
  PRIMARY KEY (LOAN_ID, CUST_ID),
  FOREIGN KEY (LOAN_ID) REFERENCES LOAN(LOAN_ID),
  FOREIGN KEY (CUST_ID) REFERENCES CUSTOMER(CUST_ID)
);

CREATE TABLE HAS
(
  CODE INT NOT NULL,
  BRANCH_ID INT NOT NULL,
  PRIMARY KEY (CODE, BRANCH_ID),
  FOREIGN KEY (CODE) REFERENCES BANK(CODE),
  FOREIGN KEY (BRANCH_ID) REFERENCES BRANCH(BRANCH_ID)
);

CREATE TABLE ACCOUNT
(
  ACCOUNT_NO INT NOT NULL,
  ACCOUNT_TYPE INT NOT NULL,
  BALANCE INT NOT NULL,
  BRANCH_ID INT NOT NULL,
  PRIMARY KEY (ACCOUNT_NO),
  FOREIGN KEY (BRANCH_ID) REFERENCES BRANCH(BRANCH_ID)
);

CREATE TABLE HOLD_BY
(
  CUST_ID INT NOT NULL,
  ACCOUNT_NO INT NOT NULL,
  PRIMARY KEY (CUST_ID, ACCOUNT_NO),
  FOREIGN KEY (CUST_ID) REFERENCES CUSTOMER(CUST_ID),
  FOREIGN KEY (ACCOUNT_NO) REFERENCES ACCOUNT(ACCOUNT_NO)
);


```

## RESULT 
<div align="justify">
Thus the ER diagram was drawn and relational diagram, SQL DDL staements are generated using ERD plus tool.
</div>
