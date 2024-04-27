# EXP NO. 4                                                                                                
# Date:26/03/2024
# AIM: 
To study and implement aggregate functions, group by and having clause with suitable examples.
# THEORY:
An aggregate function is a function that performs a calculation on a set of values, and returns a single value.
Aggregate functions are often used with the GROUP BY clause of the SELECT statement. The GROUP BY clause splits the result-set into groups of values and the aggregate function can be used to return a single value for each group.
### The most commonly used SQL aggregate functions are:
**- MIN() - returns the smallest value within the selected column**
##### Syntax: 
SELECT MIN(column_name)
FROM table_name
WHERE condition;
#### Example: SELECT MIN (Sal) FROM emp;


**- MAX() - returns the largest value within the selected column**
Syntax: 
SELECT MAX(column_name)
FROM table_name
WHERE condition;
Example: SELECT MAX (Sal) FROM emp;


COUNT() - returns the number of rows in a set
Syntax: 
SELECT COUNT(column_name)
FROM table_name
WHERE condition; 
Example: SELECT COUNT (Sal) FROM emp;


SUM() - returns the total sum of a numerical column
Syntax: 
SELECT SUM(column_name)
FROM table_name
WHERE condition;
Example: SELECT SUM (Sal) From emp;


AVG() - returns the average value of a numerical column
	Syntax: 
	SELECT AVG(column_name)
FROM table_name
WHERE condition;
	Example: Select AVG (10, 15, 30) FROM DUAL; 




GROUP BY: This query is used to group all the records in a relation together for each and every value of a specific key(s) and then display them for a selected set of fields in the relation. 
Syntax: 
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
Example: SQL> SELECT EMPNO, SUM (SALARY) FROM EMP GROUP BY EMPNO; 


GROUP BY-HAVING: The HAVING clause was added to SQL because the WHERE keyword could not be used with aggregate functions. The HAVING clause must follow the GROUP BY clause in a query and must also precede the ORDER BY clause if used. 
Syntax: 
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
