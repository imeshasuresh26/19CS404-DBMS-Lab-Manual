# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--

<img width="1205" height="777" alt="image" src="https://github.com/user-attachments/assets/6928518a-6bf9-43ce-a5c6-6b2113841427" />


```sql
SELECT p.first_name FROM PATIENTS p INNER JOIN surgeries s ON p.patient_id = s.patient_id WHERE s.surgery_date = '2024-01-15';
```

**Output:**


<img width="542" height="480" alt="image" src="https://github.com/user-attachments/assets/5dcc9fe7-945a-49cf-8249-b7103ceddb3c" />


**Question 2**
---

<img width="1212" height="742" alt="image" src="https://github.com/user-attachments/assets/fd81779a-c24d-4a1d-8bd0-1744cd8df30f" />

```sql
SELECT c.cust_name, s.name FROM customer c LEFT JOIN salesman s ON c.salesman_id = s.salesman_id WHERE c.city = s.city;
```

**Output:**


<img width="907" height="637" alt="image" src="https://github.com/user-attachments/assets/ea0217aa-84c0-48b9-b0d2-b8d4c47ca8cf" />


**Question 3**
---

<img width="1152" height="666" alt="image" src="https://github.com/user-attachments/assets/f7154bd8-0c74-44dc-908e-fcdb4cacd4bb" />


```sql
SELECT s.* FROM salesman s LEFT JOIN customer c ON s.salesman_id = c.salesman_id WHERE c.cust_name = 'Fabian Johns';
```

**Output:**


<img width="1227" height="506" alt="image" src="https://github.com/user-attachments/assets/c3d898e2-7ec2-43e0-9b82-6a329761950d" />


**Question 4**
---

<img width="1195" height="690" alt="image" src="https://github.com/user-attachments/assets/3fd2e27d-5b3d-479a-b00f-8d5d5c3c1e84" />


```sql
SELECT n.*, departments.department_name FROM nurses n INNER JOIN departments ON n.department_id = departments.department_id;
```

**Output:**


<img width="1221" height="665" alt="image" src="https://github.com/user-attachments/assets/38e9a919-e7cc-40d3-941d-2719de2bc5b8" />


**Question 5**
---




```sql
SELECT c.cust_name, c.city, o.ord_no, o.ord_date, o.purch_amt FROM customer c LEFT JOIN orders o ON c.customer_id = o.customer_id WHERE c.city = 'London';
```

**Output:**

<img width="1222" height="572" alt="image" src="https://github.com/user-attachments/assets/b8cd4166-fb39-4323-837d-9ceaf882b589" />



**Question 6**
---



```sql
SELECT salesman_name.name AS salesman_name, customer_name.cust_name AS customer_name FROM salesman salesman_name LEFT JOIN customer customer_name ON salesman_name.salesman_id = customer_name.salesman_id;
```

**Output:**




**Question 7**
---



```sql
SELECT patient_name.first_name AS patient_name, t.* FROM patients patient_name INNER JOIN test_results t ON patient_name.patient_id = t.patient_id WHERE patient_name.admission_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**





**Question 8**
---




```sql
SELECT c.* FROM customer c LEFT JOIN salesman s ON c.salesman_id = s.salesman_id WHERE s.name = 'Mc Lyon';
```

**Output:**


<img width="1230" height="497" alt="image" src="https://github.com/user-attachments/assets/9b2a02ce-8dd7-4bdf-889a-c17991168925" />

**Question 9**
---

<img width="1217" height="825" alt="image" src="https://github.com/user-attachments/assets/4bf9ff60-65ac-4620-a9fd-b852362952ea" />

```sql
SELECT s.name, c.cust_name, c.city, c.grade, c.salesman_id FROM salesman s LEFT JOIN customer c ON s.salesman_id = c.salesman_id;
```

**Output:**

<img width="1225" height="805" alt="image" src="https://github.com/user-attachments/assets/870a5913-1ba6-4187-a5bb-28fe2fe1c3d0" />


**Question 10**
---


<img width="1272" height="740" alt="image" src="https://github.com/user-attachments/assets/5bc3ff84-2327-4a3c-82d7-c8231549abd7" />

```sql
SELECT  c.cust_name AS "Customer Name", c.city, s.name AS "Salesman", s.city, s.commission FROM customer c INNER JOIN salesman s ON c.salesman_id = s.salesman_id WHERE c.city <> s.city AND s.commission > 0.12; 
```

**Output:**



<img width="1285" height="562" alt="image" src="https://github.com/user-attachments/assets/d2fefb6d-bfa8-40e3-9ddd-f9a91add6530" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
