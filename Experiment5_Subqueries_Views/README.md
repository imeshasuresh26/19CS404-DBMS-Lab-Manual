# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--

<img width="1121" height="570" alt="image" src="https://github.com/user-attachments/assets/6713db8c-a8f6-432a-8cc8-ed67d6363897" />


```sql
SELECT name, city FROM customer WHERE city IN(SELECT city FROM customer WHERE id IN (3, 7));
```

**Output:**


<img width="707" height="537" alt="image" src="https://github.com/user-attachments/assets/de3aa28d-1400-49c8-8a72-ea9c6b39f877" />


**Question 2**
---

<img width="1205" height="730" alt="image" src="https://github.com/user-attachments/assets/d2f87e5b-6b65-40b7-abd4-8cbf5fe42c6f" />

```sql
SELECT o.ord_no,o.purch_amt,o.ord_date,o.customer_id,o.salesman_id FROM Orders o JOIN Salesman s ON o.salesman_id=s.salesman_id WHERE s.city = 'New York';
```

**Output:**


<img width="1221" height="552" alt="image" src="https://github.com/user-attachments/assets/8ed65eca-0639-48ce-bd63-808828cf74c9" />


**Question 3**
---

<img width="1140" height="462" alt="image" src="https://github.com/user-attachments/assets/8a86b3e6-4ba5-402a-8af2-fc63c28931c2" />


```sql
SELECT * FROM Departments WHERE LENGTH(department_name) > (SELECT AVG(LENGTH(department_name)) FROM Departments);
```

**Output:**


<img width="727" height="491" alt="image" src="https://github.com/user-attachments/assets/737670a7-2b0a-44ad-b20c-628ded1ab0bf" />

**Question 4**
---

<img width="1022" height="687" alt="image" src="https://github.com/user-attachments/assets/6db31f20-3f66-4bda-8e49-452818e92fe5" />


```sql
SELECT * FROM CUSTOMERS WHERE SALARY > 4500;
```

**Output:**


<img width="1227" height="522" alt="image" src="https://github.com/user-attachments/assets/82ca25da-a0d7-4576-b587-5922fdce1758" />

**Question 5**
---

<img width="982" height="647" alt="image" src="https://github.com/user-attachments/assets/9bd6da0b-c04b-4502-8623-991f902340c0" />

```sql
SELECT * FROM CUSTOMERS WHERE ADDRESS = 'Delhi';
```

**Output:**



<img width="1235" height="425" alt="image" src="https://github.com/user-attachments/assets/f35a924f-edfc-4c75-ac99-0eec13227646" />


**Question 6**
---


<img width="1202" height="655" alt="image" src="https://github.com/user-attachments/assets/871cb26e-0ed8-4b1a-8c9e-7950f45b39af" />

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id FROM Orders WHERE salesman_id = ( SELECT salesman_id FROM Salesman WHERE name = 'Paul Adam');
```

**Output:**


<img width="1227" height="487" alt="image" src="https://github.com/user-attachments/assets/e9d25197-cff9-47b3-8e8e-57d09c69739b" />

**Question 7**
---




```sql
SELECT * FROM Employee WHERE age < ( SELECT AVG(age) FROM Employee WHERE income > 250000);
```

**Output:**


<img width="1237" height="612" alt="image" src="https://github.com/user-attachments/assets/82a5b46e-6805-4be4-a474-9a760e3809cd" />


**Question 8**
---

<img width="1192" height="672" alt="image" src="https://github.com/user-attachments/assets/efe94389-0941-45f0-a084-4ce22f272196" />


```sql
SELECT * FROM GRADES g1 WHERE grade = ( SELECT MAX(grade) FROM GRADES g2 WHERE g1.subject = g2.subject);
```

**Output:**


<img width="1231" height="542" alt="image" src="https://github.com/user-attachments/assets/9d1527ac-ddd7-4d8e-b04a-871d52928025" />


**Question 9**
---

<img width="1175" height="852" alt="image" src="https://github.com/user-attachments/assets/35e680e9-4640-4006-af44-82d6a85c2119" />


```sql
SELECT ord_no, purch_amt, ord_date, salesman_id FROM orders WHERE salesman_id IN ( SELECT salesman_id FROM salesman WHERE commission = (SELECT MAx(commission) FROM salesman));
```

**Output:**


<img width="1067" height="552" alt="image" src="https://github.com/user-attachments/assets/7b549c76-162b-4a3a-a28f-2ddb4bc45a6a" />


**Question 10**
---

<img width="1192" height="541" alt="image" src="https://github.com/user-attachments/assets/430f78ef-bd6b-4a70-8a46-415631b3754f" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id FROM orders WHERE salesman_id IN ( SELECT salesman_id FROM orders WHERE customer_id = 3007);
```

**Output:**



<img width="1236" height="527" alt="image" src="https://github.com/user-attachments/assets/55994ee4-3e0f-4884-8623-8bb66f48b652" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
