# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
<img width="913" height="208" alt="image" src="https://github.com/user-attachments/assets/f98b68a0-8886-4f26-b40a-cffcd0184b2d" />
```
DELETE FROM Doctors WHERE doctor_id=1;
```
**Output:**

<img width="1223" height="351" alt="image" src="https://github.com/user-attachments/assets/237d4ed1-2b17-4627-a04c-6ce42f2a6690" />


**Question 2**
<img width="798" height="116" alt="image" src="https://github.com/user-attachments/assets/b97677ae-1c2e-4dd6-985d-e529d07f428e" />

```
UPDATE Customer SET grade =5 WHERE city ='Chennai';
```
**Output:**

<img width="1232" height="553" alt="image" src="https://github.com/user-attachments/assets/804cdb7f-61d5-4548-8b41-93b5ee4063e8" />


**Question 3**

<img width="1232" height="645" alt="image" src="https://github.com/user-attachments/assets/89f4fafa-3c73-432b-b534-e364a3ef2ce4" />
```
SELECT * FROM orders WHERE ord_date <> '2012-08-17' AND NOT (CUSTOMER_ID > 3005 AND purch_amt < 1000);
```

**Output:**


<img width="1222" height="822" alt="image" src="https://github.com/user-attachments/assets/7a8e0606-c398-47c2-80cd-d643d34bba13" />


**Question 4**

<img width="1183" height="513" alt="image" src="https://github.com/user-attachments/assets/196c7c32-941a-4787-a226-9d9f38f25c8c" />
```
UPDATE Products SET reorder_lvl =20 WHERE quantity < 10 AND category = 'Snacks';
```
**Output:**


<img width="1235" height="665" alt="image" src="https://github.com/user-attachments/assets/c90d9fb6-eea5-4848-9c42-4d2d080f0513" />


**Question 5**

<img width="1223" height="577" alt="image" src="https://github.com/user-attachments/assets/7a116853-dd9e-49af-9a66-7ca288fe7d61" />
```
SELECT
      product_id,
      original_price,
      discount_percentage,
      (original_price * discount_percentage) AS discount_amount 
FROM 
       products 
WHERE 
       (original_price * discount_percentage) > 50;
```
**Output:**


<img width="1236" height="356" alt="image" src="https://github.com/user-attachments/assets/2cd7c9e1-2e46-4683-9eb5-a89f0f113fb8" />


**Question 6**

<img width="916" height="227" alt="image" src="https://github.com/user-attachments/assets/b38ffc5e-e85c-4572-a244-2b111097652a" />
```
UPDATE products 
SET availability = availability*2
WHERE product_id = 1;
```
**Output:**


<img width="1230" height="328" alt="image" src="https://github.com/user-attachments/assets/563c7420-3a5d-42ab-a779-8ee23bc3b67b" />


**Question 7**

<img width="1228" height="523" alt="image" src="https://github.com/user-attachments/assets/1a6fe4a9-b4ed-448b-99e3-1614279821b4" />

```
DELETE FROM customer WHERE CUST_CITY != 'New York' AND OUTSTANDING_AMT > 5000;
```
**Output:**


<img width="1222" height="645" alt="image" src="https://github.com/user-attachments/assets/06046146-6b0a-424b-b015-c297e2833d16" />


**Question 8**

<img width="1235" height="703" alt="image" src="https://github.com/user-attachments/assets/6aad45df-ef99-4ae8-a31b-a67c49f53a97" />
```
DELETE FROM customer  WHERE GRADE < 2;
```
**Output:**


<img width="786" height="640" alt="image" src="https://github.com/user-attachments/assets/dcc5df6e-211a-4d82-a18f-27c796c57164" />


**Question 9**

<img width="1171" height="612" alt="image" src="https://github.com/user-attachments/assets/757e622a-f475-475a-a004-39d79dce679c" />

```
SELECT product_id,original_price,discount_percentage,(original_price *(1- discount_percentage)) AS discounted_price FROM Products WHERE discount_percentage >0 ORDER BY discounted_price ASC;
```
**Output:**

<img width="1235" height="372" alt="image" src="https://github.com/user-attachments/assets/ca1c5d9b-9c21-484a-9636-36b42dae4317" />


**Question 10**

<img width="1230" height="652" alt="image" src="https://github.com/user-attachments/assets/a28d4b42-621a-449c-9049-ae5d6433238e" />
```
UPDATE employees SET salary=salary*2 WHERE department_id =20 AND job_id LIKE '%MAN';
```
**Output:**


<img width="1223" height="422" alt="image" src="https://github.com/user-attachments/assets/bb6a4c40-c3a7-483b-92bc-2c103ba00ee8" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
