# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
<img width="1207" height="475" alt="image" src="https://github.com/user-attachments/assets/f3c98f27-2311-4f3b-8191-b2cc003de84f" />
```
CREATE TABLE products(product_id INTEGER PRIMARY KEY,product_name TEXT NOT NULL,list_price DECIMAL(10,2) NOT NULL,discount DECIMAL(10,2) NOT NULL DEFAULT 0,CHECK(list_price>=discount ANd discount >=0 AND list_price>=0));
```

**Output:**

<img width="1208" height="368" alt="image" src="https://github.com/user-attachments/assets/6e541747-c012-4fb5-b1b3-8ab129cb31be" />


**Question 2**
<img width="990" height="415" alt="image" src="https://github.com/user-attachments/assets/5864b54b-6e7b-4bf9-b803-c889806120a2" />

```
CREATE TABLE orders(OrderID INTEGER ,OrderDate TEXT,CustomerID INTEGER);
```
**Output:**

<img width="1237" height="466" alt="image" src="https://github.com/user-attachments/assets/354c0822-8f05-4851-8e76-557b8e7bab45" />


**Question 3**
<img width="1065" height="387" alt="image" src="https://github.com/user-attachments/assets/d9327792-cb89-4e30-9d48-a755854c99bd" />
```
CREATE TABLE Events(EventID INTEGER , EventName TEXT, EventDate DATE);
```

**Output:**

<img width="1240" height="448" alt="image" src="https://github.com/user-attachments/assets/a138ecf1-e949-42cb-9db9-61694f421df0" />


**Question 4**
<img width="1212" height="521" alt="image" src="https://github.com/user-attachments/assets/020a03f9-4afc-4d52-9f4e-7347e08b3393" />
```
INSERT INTO Products(ProductID,Name,Category,Price,Stock) VALUES(106,'Fitness Tracker','Wearables',NULL,NULL);
INSERT INTO Products(ProductID,Name,Category,Price,Stock) VALUES(107,'Laptop','Electronics',999.99,50);
INSERT INTO Products(ProductID,Name,Category,Price,Stock) VALUES(108,'Wireless Earbuds','Accessories',NULL,100);
```

**Output:**

<img width="1228" height="376" alt="image" src="https://github.com/user-attachments/assets/5dcf0b69-9074-4a82-b10e-759cb7783ce5" />


**Question 5**



<img width="1197" height="607" alt="image" src="https://github.com/user-attachments/assets/a904f9c3-a25a-410a-b300-c8a6eec95025" />

```
ALTER TABLE Student_details ADD COLUMN State TEXT;
```
**Output:**


<img width="1225" height="446" alt="image" src="https://github.com/user-attachments/assets/a8fea1d1-62cc-404a-adce-e7b76e741c67" />


**Question 6**

<img width="1161" height="368" alt="image" src="https://github.com/user-attachments/assets/93b69394-2ec2-4a74-aa9c-1bf086e86923" />
```
ALTER TABLE employee ADD COLUMN first_name varchar(50);
ALTER TABLE employee ADD COLUMN last_name varchar(50);
```

**Output:**


<img width="1232" height="408" alt="image" src="https://github.com/user-attachments/assets/b88fcb0b-571e-413c-96fd-192e2471476c" />


**Question 7**

<img width="1052" height="468" alt="image" src="https://github.com/user-attachments/assets/775eb880-b8cf-44a0-8126-a6e53c93bc5a" />
```
CREATE TABLE Reviews(ReviewID INTEGER,ProductID INTEGER,Rating REAL,ReviewText TEXT);
```

**Output:**


<img width="1223" height="486" alt="image" src="https://github.com/user-attachments/assets/a8d128f4-86b3-4e28-a3b4-e296ab8bb3f7" />


**Question 8**

<img width="1013" height="498" alt="image" src="https://github.com/user-attachments/assets/3d178761-04de-4a13-9966-a780808994b3" />

```
INSERT INTO Student_details SELECT * FROM Archived_students;
```
**Output:**


<img width="1236" height="378" alt="image" src="https://github.com/user-attachments/assets/4862f51a-ba3a-4690-ac1e-5cc95e4d71b1" />


**Question 9**

<img width="1202" height="503" alt="image" src="https://github.com/user-attachments/assets/234c05c7-1051-4344-9801-b3bf7bacdaf1" />
```
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)VALUES(5,'George Clark','Consultant',NULL,NULL);
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)VALUES(7,'Noah Davis','Manager','HR',60000);
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)VALUES(8,'Ava Miller','Consultant','IT',NULL);
```
**Output:**


<img width="1231" height="387" alt="image" src="https://github.com/user-attachments/assets/70ea3b78-348f-49d0-8f31-9346deee8b63" />

**Question 10**

<img width="1227" height="387" alt="image" src="https://github.com/user-attachments/assets/3eb9cc9d-ffa1-48fe-8c17-c8b8f24e1908" />

```
CREATE TABLE contacts(contact_id INTEGER PRIMARY KEY,first_name TEXT NOT NULL,last_name TEXT NOT NULL,email TEXT,phone TEXT NOT NULL,CHECK (LENGTH(phone)>=10));
```

**Output:**


<img width="1228" height="416" alt="image" src="https://github.com/user-attachments/assets/fbb8f29a-0f42-4420-b6c1-2b06caa77290" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
