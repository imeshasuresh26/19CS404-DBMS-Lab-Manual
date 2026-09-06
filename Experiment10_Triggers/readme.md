# Experiment 10: PL/SQL – Triggers

## AIM
To write and execute PL/SQL trigger programs for automating actions in response to specific table events like INSERT, UPDATE, or DELETE.

---

## THEORY

A **trigger** is a stored PL/SQL block that is automatically executed or fired when a specified event occurs on a table or view. Triggers can be used for enforcing business rules, auditing changes, or automatic updates.

### Types of Triggers:
- **Before Trigger**: Executes before the operation (INSERT, UPDATE, DELETE).
- **After Trigger**: Executes after the operation.
- **Row-level Trigger**: Executes for each affected row.
- **Statement-level Trigger**: Executes once for the triggering statement.

**Basic Syntax:**
```sql
CREATE OR REPLACE TRIGGER trigger_name
BEFORE|AFTER INSERT|UPDATE|DELETE ON table_name
[FOR EACH ROW]
BEGIN
   -- trigger logic
END;
```

## 1. Write a trigger to log every insertion into a table.
**Steps:**
- Create two tables: `employees` (for storing data) and `employee_log` (for logging the inserts).
- Write an **AFTER INSERT** trigger on the `employees` table to log the new data into the `employee_log` table.

### PROGRAM
<img width="645" height="447" alt="image" src="https://github.com/user-attachments/assets/b5205eb4-826b-43a1-8798-33a28ea63c30" />

**Expected Output:**
- A new entry is added to the `employee_log` table each time a new record is inserted into the `employees` table.
<img width="570" height="181" alt="image" src="https://github.com/user-attachments/assets/003cbacb-44de-4bcf-b221-62a55eb265be" />

---

## 2. Write a trigger to prevent deletion of records from a sensitive table.
**Steps:**
- Write a **BEFORE DELETE** trigger on the `sensitive_data` table.
- Use `RAISE_APPLICATION_ERROR` to prevent deletion and issue a custom error message.
 ### PROGRAM
 <img width="777" height="337" alt="image" src="https://github.com/user-attachments/assets/b16e3aeb-00f1-47d2-8331-f95d85994258" />


**Expected Output:**
- If an attempt is made to delete a record from `sensitive_data`, an error message is raised, e.g., `ERROR: Deletion not allowed on this table.`
<img width="737" height="442" alt="image" src="https://github.com/user-attachments/assets/edaade6e-df9d-4dcd-900b-191ef93ebdf6" />

---

## 3. Write a trigger to automatically update a `last_modified` timestamp.
**Steps:**
- Add a `last_modified` column to the `products` table.
- Write a **BEFORE UPDATE** trigger on the `products` table to set the `last_modified` column to the current timestamp whenever an update occurs.
### PROGRAM
<img width="526" height="417" alt="image" src="https://github.com/user-attachments/assets/21400230-3e44-474d-a049-a91263644db3" />

**Expected Output:**
- The `last_modified` column in the `products` table is updated automatically to the current date and time when any record is updated.
<img width="937" height="230" alt="image" src="https://github.com/user-attachments/assets/9b9de86f-1cda-4ec7-88dc-fa8e53f5e178" />

---

## 4. Write a trigger to keep track of the number of updates made to a table.
**Steps:**
- Create an `audit_log` table with a counter column.
- Write an **AFTER UPDATE** trigger on the `customer_orders` table to increment the counter in the `audit_log` table every time a record is updated.
### PROGRAM
<img width="511" height="467" alt="image" src="https://github.com/user-attachments/assets/85bd5121-d292-44b7-966f-e244b065e338" />

**Expected Output:**
- The `audit_log` table will maintain a count of how many updates have been made to the `customer_orders` table.
<img width="550" height="172" alt="image" src="https://github.com/user-attachments/assets/a5b32db0-3735-4e95-b494-ee0fc677f2d3" />

---

## 5. Write a trigger that checks a condition before allowing insertion into a table.
**Steps:**
- Write a **BEFORE INSERT** trigger on the `employees` table to check if the inserted salary meets a specific condition (e.g., salary must be greater than 3000).
- If the condition is not met, raise an error to prevent the insert.
### PROGRAM
<img width="762" height="377" alt="image" src="https://github.com/user-attachments/assets/87edacfa-159a-4c7f-aad9-39759c60f925" />

**Expected Output:**
- If the inserted salary in the `employees` table is below the condition (e.g., salary < 3000), the insert operation is blocked, and an error message is raised, such as: `ERROR: Salary below minimum threshold.`
<img width="480" height="235" alt="image" src="https://github.com/user-attachments/assets/ebd5db55-ed0b-49f2-87b8-87aed78b8148" />

## RESULT
Thus, the PL/SQL trigger programs were written and executed successfully.
