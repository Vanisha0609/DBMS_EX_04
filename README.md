# EXP NO. 4                                                                                                
# Date:26/03/2024
# AIM: 
To study and implement aggregate functions, group by and having clause with suitable examples.
# THEORY:
An aggregate function is a function that performs a calculation on a set of values, and returns a single value.
Aggregate functions are often used with the GROUP BY clause of the SELECT statement. The GROUP BY clause splits the result-set into groups of values and the aggregate function can be used to return a single value for each group.
## The most commonly used SQL aggregate functions are:
### - MIN() 
Returns the smallest value within the selected column
#### Syntax: 
```
SELECT MIN(column_name)
FROM table_name
WHERE condition;
```
#### Example:
SELECT MIN (Sal) FROM emp;

### - MAX() 
Returns the largest value within the selected column
#### Syntax: 
```
SELECT MAX(column_name)
FROM table_name
WHERE condition;
```
#### Example:
SELECT MAX (Sal) FROM emp;

### - COUNT() 
Returns the number of rows in a set
#### Syntax: 
```
SELECT COUNT(column_name)
FROM table_name
WHERE condition;
```
#### Example: 
SELECT COUNT (Sal) FROM emp;

### - SUM() 
Returns the total sum of a numerical column
#### Syntax: 
```
SELECT SUM(column_name)
FROM table_name
WHERE condition;
```
#### Example: 
SELECT SUM (Sal) From emp;

### - AVG()
Returns the average value of a numerical column
#### Syntax: 
```
SELECT AVG(column_name)
FROM table_name
WHERE condition;
```
#### Example: 
Select AVG (10, 15, 30) FROM DUAL;

## GROUP BY: 
This query is used to group all the records in a relation together for each and every value of a specific key(s) and then display them for a selected set of fields in the relation. 
### Syntax: 
```
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```
### Example: 
SQL> SELECT EMPNO, SUM (SALARY) FROM EMP GROUP BY EMPNO; 

## GROUP BY-HAVING: 
The HAVING clause was added to SQL because the WHERE keyword could not be used with aggregate functions. The HAVING clause must follow the GROUP BY clause in a query and must also precede the ORDER BY clause if used. 
### Syntax: 
```
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```
# MODULE:
## QUESTION 1 :
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/4eaf0c54-2e87-4e6b-8701-814863b696ac)

### QUERY:
```
SELECT DoctorID, COUNT(*) AS TotalPrescriptions
FROM Prescriptions
GROUP BY DoctorID;
```
### OUTPUT:
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/f43fdd87-c78c-47e1-8c09-9ffccb1314c3)

## QUESTION 2 :
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/f3ee451c-0d8c-4075-9629-00efd2d374de)

### QUERY:
```
SELECT Medication,AVG(Dosage) as AvgDosage
FROM Prescriptions
GROUP BY Medication;
```
### OUTPUT:
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/0d00762a-d796-4d56-8f95-381707c6c171)

## QUESTION 3 :
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/fd1209ad-227a-45b7-8f57-6eb33bc4ad0a)


### QUERY:
```
SELECT PatientID ,COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID ;

```
### OUTPUT:
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/71e9589d-f70d-4f45-8e39-d1a45cb5ca26)

## QUESTION 4 :
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/3604e10f-091f-4ee5-839c-4fe53c6c2632)

### QUERY:
```
SELECT MAX(price) - MIN(price) AS price_diff
FROM fruits;
```
### OUTPUT:
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/a617929a-3fc2-4344-8931-3c852b8cd0f0)

## QUESTION 5 :
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/fe287cd5-5c43-4e76-a21c-674576f528d2)

### QUERY:
```
SELECT COUNT(*) AS COUNT
FROM customer;
```
### OUTPUT:
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/ba829c47-4d2d-425f-b67e-62e605cfd1dc)


## QUESTION 6 :
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/a93445fb-5e7e-453c-acf2-639565caf05d)

### QUERY:
```
SELECT COUNT(DISTINCT salesman_id) AS COUNT
FROM orders;
```
### OUTPUT:
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/28c2c62f-f0aa-487e-8375-5adc382c4ec3)

## QUESTION 7 :
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/6c5cb5ec-aa88-4e13-a998-454d2d2e989c)

### QUERY:
```
SELECT MAX(purch_amt) AS MAXIMUM
FROM orders;
```
### OUTPUT:
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/25c30efd-41ee-48e6-a1b1-0608eed0286e)

## QUESTION 8 :
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/d41a8872-3b2f-42a9-a178-7004372aabd5)
### QUERY:
```
SELECT category_id, COUNT(*) AS COUNT
FROM products
WHERE category_id > 2
GROUP BY category_id;
```
### OUTPUT:
![image](https://github.com/Vanisha0609/DBMS_EX_04/assets/119104009/b5b021b4-5bf3-468b-8515-21afa72aba74)

## QUESTION 9 :
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/4402ff66-fcfd-4092-af30-57fc37d4e0cb)

### QUERY:
```
SELECT (age/5)*5 AS age_group, MIN(age) AS `MIN(age)`
FROM customer1
GROUP BY age_group
HAVING  MIN(age) < 25;

```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/40d52f15-2f10-4234-9b66-632d1efa2799)

## QUESTION 10 :
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/59214144-6dca-4d26-8204-56ae28cbfa17)

### QUERY:
```
SELECT occupation,MIN(workhour) AS 'MIN(workhour)'
FROM employee1
GROUP BY occupation
HAVING MIN(workhour)>8;
```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/aa91f685-4b5f-4225-8c81-a584d0c52da6)

# RESULT:
Thus, we studied and implemented the aggregate functions, group by and having clause with suitable examples.

