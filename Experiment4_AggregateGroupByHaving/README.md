# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**

<img width="1052" height="481" alt="image" src="https://github.com/user-attachments/assets/69bd94d7-03ac-410b-a3c7-40d923274e0e" />


``sql
SELECT AVG(LENGTH(email)) AS avg_email_length_below_30 FROM customer WHERE city = 'Mumbai';


```

**Output:**

<img width="695" height="407" alt="image" src="https://github.com/user-attachments/assets/de82534b-d37c-4467-ae3c-f5f1cffafe27" />


**Question 2**

<img width="967" height="485" alt="image" src="https://github.com/user-attachments/assets/cedbabb9-3038-4a98-b9d6-35f1dde44838" />


```sql
SELECT SUM(purch_amt) AS TOTAL FROM orders;
```

**Output:**

<img width="475" height="385" alt="image" src="https://github.com/user-attachments/assets/611620ba-c32e-4967-b10b-55f765a0ee35" />

**Question 3**
---
<img width="1110" height="496" alt="image" src="https://github.com/user-attachments/assets/5c7c9f3d-f6b6-4c59-bae8-96308baf59c6" />


```sql
SELECT COUNT(DISTINCT age) AS COUNT FROM employee;
```

**Output:**

<img width="497" height="411" alt="image" src="https://github.com/user-attachments/assets/3609b9e9-8c20-4f80-bc87-71a5f3f5627e" />

**Question 4**
---
<img width="1050" height="587" alt="image" src="https://github.com/user-attachments/assets/92a02449-43ab-40c1-95d7-37879fbe12a9" />

```sql
SELECT Specialty, Gender, COUNT(*) AS TotalDoctors FROM Doctors GROUP BY Specialty, Gender;
```

**Output:**

<img width="1087" height="726" alt="image" src="https://github.com/user-attachments/assets/019177ad-c13c-449b-81d2-25c0408905a7" />

**Question 5**
---


<img width="1037" height="647" alt="image" src="https://github.com/user-attachments/assets/116388bf-f9d6-471f-a921-bd601cc339b2" />

```sql
SELECT Medication, AVG(Dosage) AS AvgDosage FROM Prescriptions GROUP BY Medication;
```

**Output:**


<img width="936" height="817" alt="image" src="https://github.com/user-attachments/assets/dccdf0ae-b098-40fc-ac30-91ebd615a66e" />


**Question 6**
---

<img width="1162" height="585" alt="image" src="https://github.com/user-attachments/assets/34de8a98-6e17-4aac-bf13-2a34938d946f" />

```sql

SELECT Specialty, ROUND(AVG(CAST(CAST((strftime('%Y%m%d', '2024-07-01') AS INTEGER) - CAST(strftime('%Y%m%d', DateOfBirth)) AS INTEGER)) / 10000 AS REAL)), 1) AS AvgAge FROM Doctors GROUP BY Specialty;
```

**Output:**


<img width="816" height="817" alt="image" src="https://github.com/user-attachments/assets/7c78df2a-85a5-41e9-acdf-66d2dbf06edf" />


**Question 7**
---

<img width="1210" height="495" alt="image" src="https://github.com/user-attachments/assets/ff00177f-e35a-48b7-96c5-bd6cdc6cccf4" />

```sql
SELECT (age/5)*5 AS age_group, SUM(salary) FROM customer1 GROUP BY (age/5)*5 HAVING SUM(salary) > 5000;
```

**Output:**


<img width="772" height="442" alt="image" src="https://github.com/user-attachments/assets/ca56dff3-9294-4a8e-897c-f96b337fbda7" />

**Question 8**
---

<img width="1211" height="542" alt="image" src="https://github.com/user-attachments/assets/3103baa8-429d-4887-a2ce-89106478726e" />

```sql
SELECT category_id, SUM(price * category_id) AS Revenue FROM products GROUP BY category_id HAVING SUM(price * category_id) > 25;
```

**Output:**


<img width="767" height="517" alt="image" src="https://github.com/user-attachments/assets/568ea2ee-8235-446a-b3d6-2b62058ffa50" />

**Question 9**
---

<img width="1227" height="530" alt="image" src="https://github.com/user-attachments/assets/bff7f102-f43a-494f-b6b6-cb24bae881b9" />

```sql
SELECT age, SUM(income) FROM employee GROUP BY age HAVING SUM(income) > 1000000;
```

**Output:**


<img width="672" height="482" alt="image" src="https://github.com/user-attachments/assets/8e3237db-989a-444a-9079-6e1a26ef671e" />


**Question 10**
---

<img width="1207" height="512" alt="image" src="https://github.com/user-attachments/assets/45f234ed-9577-4130-9973-75a7e3975686" />


```sql
SELECT occupation, AVG(workhour) FROM employee1 GROUP BY occupation HAVING AVG(workhour) BETWEEN 10 AND 12;
```

**Output:**


<img width="687" height="470" alt="image" src="https://github.com/user-attachments/assets/cab61feb-00f3-4737-b193-369581f23ac8" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
