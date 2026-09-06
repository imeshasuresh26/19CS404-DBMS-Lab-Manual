# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Greater number is: 80

### PROGRAM:
<img width="740" height="232" alt="image" src="https://github.com/user-attachments/assets/c455f4d4-96c5-45ea-ba5e-233e0737e08a" />

### OUTPUT:
<img width="492" height="242" alt="image" src="https://github.com/user-attachments/assets/7ce582fd-08de-4d93-b191-f438c258b6f7" />

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55

---
### PROGRAM

<img width="715" height="286" alt="image" src="https://github.com/user-attachments/assets/1970216d-29e2-4bf6-b930-703e4174f45c" />

### OUTPUT:

<img width="502" height="232" alt="image" src="https://github.com/user-attachments/assets/f5f6851b-e513-42fc-be96-ba6fc8f98d16" />

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

---
### PROGRAM:

<img width="645" height="412" alt="image" src="https://github.com/user-attachments/assets/5b75b4db-a81e-4bea-bcc3-46b8e590dab8" />


### OUTPUT:

<img width="487" height="377" alt="image" src="https://github.com/user-attachments/assets/79dfc2dc-7897-4295-822d-d0547030797e" />

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351

---

### PROGRAM:

<img width="602" height="287" alt="image" src="https://github.com/user-attachments/assets/79f502b5-533c-4e43-83b4-45e6a17a4f70" />


### OUTPUT:

<img width="517" height="250" alt="image" src="https://github.com/user-attachments/assets/ba70cec6-b482-48c2-b951-9ed4155669b9" />


## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

### PROGRAM

<img width="502" height="225" alt="image" src="https://github.com/user-attachments/assets/737e3b1b-0dbc-4ba0-9700-8fb14923ddec" />

### OUTPUT:
<img width="731" height="390" alt="image" src="https://github.com/user-attachments/assets/94d11066-fbf0-4a6f-a73d-5ab9d913a05a" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
