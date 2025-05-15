# Section 2: Single Table Queries
---
## Lesson #4: Retrieving Data From A Table (SELECT Clause)
## Lesson #5: Using the WHERE Clause In a SQL Query
## Lesson #6: Using Operators in the WHERE Clause
## Lesson #7: Combining WHERE, AND, & OR with Operators
## Lesson #8: Query Filtering Continued BETWEEN, IN and NULL
## Lesson #9: Query Filtering Conditions & Operator Precendence
---
`SELECT * FROM EMP
WHERE (COMM IS NULL OR COMM = 0)
AND SAL > 1100 AND SAL < 5000
AND SAL != 1500; (or use <>)` 
- In SQL, group all ands together or use parentheses

- Return those employees that are salesmen and that make either 300 dollars in commission or greater than 1000 dollars in commission
`SELECT * FROM EMP
WHERE JOB = 'SALESMAN
AND (COMM = 300 OR COMM > 1000);`

- LIKE Operator
`SELECT * FROM EMP
WHERE JOB LIKE 'S%';`

# Lesson 10: Ordering, Concatenating, and Aliasing Query Results
---
`SELECT * FROM EMP;`
`SELECT ENMAE, SAL, COMM FROM EMP;`
`SELECT ENAME EMPLOYEE, SAL SALARY, COMM COMMISSION FROM EMP;`
`SELECT ENAME EMPLOYEE_NAME FROM EMP;`
`SELECT ENAME "EMPLOYEE NAME" FROM EMP;`

- Oracle SQL Standard
`SELECT ENAME AS "employee name" FROM EMP;`

- Print out sentence
`SELECT 'hello, my name is '|| ENAME AS "CONCATENATED VALUE"
FROM EMP
WHERE JOB = 'MANAGER';`

- Create a report that says ename makes sal per month
`SELECT ENAME || ' makes $' || SAL || ' per month' AS "New Report" 
FROM EMP;`

- ORDER BY (Data sorted by ascending (ASC) by default)
`SELECT ENAME, SAL 
FROM EMP
ORDER BY ENAME DESC;`

- Can order by multiple columns 
`SELECT DEPTNO, SAL, ENAME
FROM EMP
ORDER BY DEPTNO, SAL;`
