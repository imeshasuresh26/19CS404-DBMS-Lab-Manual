# Experiment 9: PL/SQL – Procedures and Functions

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.

### Program
<img width="1000" height="335" alt="image" src="https://github.com/user-attachments/assets/bdaebbea-36df-4bd7-acaa-e6be4c2c1ad9" />

**Expected Output:**  
Square of 6 is 36

<img width="676" height="406" alt="image" src="https://github.com/user-attachments/assets/9f4fc367-b117-4da8-a433-73498b7994a9" />

---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.
 ### Program

 <img width="791" height="321" alt="image" src="https://github.com/user-attachments/assets/ae45083a-ce5b-4c36-a73e-fe0db6e31c05" />

**Expected Output:**  
Factorial of 5 is 120


<img width="640" height="302" alt="image" src="https://github.com/user-attachments/assets/32929ab2-d7a8-4218-8e2a-d8b4a1a73d1e" />

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

### Program

<img width="912" height="437" alt="image" src="https://github.com/user-attachments/assets/3dc53ccc-47c1-45f7-bd05-87f335678098" />

**Expected Output:**  
12 is Even
<img width="731" height="437" alt="image" src="https://github.com/user-attachments/assets/24d5e5ac-43b1-4163-97dc-ccb1a9531ef3" />

---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

### Program
<img width="850" height="391" alt="image" src="https://github.com/user-attachments/assets/c763636f-11e7-4bbc-ab64-216a0fc9e93d" />

**Expected Output:**  
Reversed number of 1234 is 4321

<img width="532" height="287" alt="image" src="https://github.com/user-attachments/assets/32e0d4d1-d4da-40cf-a30b-3cfb21c4693f" />

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.
### Program
<img width="1017" height="401" alt="image" src="https://github.com/user-attachments/assets/bc2de349-0602-43ff-8a9a-83fae5984584" />

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50
<img width="745" height="517" alt="image" src="https://github.com/user-attachments/assets/de72f854-105b-4173-980e-edba2e6eff46" />

## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
