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
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/12a7cd35-3740-4850-8815-a99d1c50b8fe)

### QUERY:
```
SELECT InsuranceCompany, AVG((EndDate) - (StartDate)) AS AvgCoverageDurationDays
FROM Insurance
GROUP BY InsuranceCompany;

```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/b6836759-b82c-4fa0-b254-acd7fc96fb30)

## QUESTION 2 :
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/f0ef827c-6278-4ba1-80d5-3093288913d8)

### QUERY:
```
SELECT Medication, COUNT(*) AS TotalPrescriptions
FROM Prescriptions
GROUP BY Medication;

```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/40a875dd-6d40-434a-a93b-cbc32fe46f98)

## QUESTION 3 :
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/d7fc61b2-0e77-4526-b3df-5265a72d3d5c)

### QUERY:
```
SELECT strftime('%Y-%m', Date) AS Month, COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY strftime('%Y-%m', Date);

```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/fbf0c8c5-6dd8-45ba-9d6d-d9e2a9db518e)

## QUESTION 4 :
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/0e411117-694b-4e5f-928d-975322d9bb1c)

### QUERY:
```
SELECT MAX(price) - MIN(price) AS price_diff
FROM fruits;
```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/80cd0f04-75d0-476f-b165-fa2e8a80e1e4)

## QUESTION 5 :
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/a7a41117-f7da-45d2-89d2-6a33ab234ef8)

### QUERY:
```
SELECT COUNT(DISTINCT salesman_id) AS COUNT
FROM orders;
```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/267ccbd0-adae-4523-9568-b7e20af9bc0b)

## QUESTION 6 :
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/924d7899-23e0-44e6-96b0-63e6ffd632e8)

### QUERY:
```
SELECT COUNT(DISTINCT city)AS unique_cities
FROM customer;
```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/05f4faf7-0a8d-44c8-b937-1e3b7ff5fce4)

## QUESTION 7 :
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/a80921c5-bec0-4f82-a602-186133a6be2b)

### QUERY:
```
SELECT name,MAX(income) AS 'max(income)'  
FROM employee
WHERE city='California';
```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/1d5043e6-839a-4900-b7fe-796d67490d75)

## QUESTION 8 :
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/b0a3296e-8a32-478f-8be5-3b524b6e4c22)

### QUERY:
```
SELECT age, SUM(income) AS `SUM(income)`
FROM employee
GROUP BY age
HAVING SUM(income) > 1000000;
```
### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_04/assets/102855266/d2b8c661-8785-48aa-ad05-efa8bdd52dd4)

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

