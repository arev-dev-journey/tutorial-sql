# Section 2: Single Table Queries
---
## Lesson #4: Retrieving Data From A Table (SELECT Clause)
---
`SELECT * FROM EMP;`
`SELECT <column1, col2, ...>
FROM <table>`
`SELECT DISTINCT JOB FROM EMP;`

## Lesson #5: Using the WHERE Clause In a SQL Query
---
`SELECT * FROM EMP;`
`SELECT ENAME 
FROM EMP
WHERE JOB = 'MANAGER'
AND SAL = 1600;`
## Lesson #6: Using Operators in the WHERE Clause
---
`SELECT * FROM EMP
WHERE JOB != 'SALESMAN'
AND SAL <= 3000;`

`SELECT * FROM EMP
WHERE SAL < COMM;`

`SELECT * FROM EMP
WHERE JOB != 'MANAGER'
AND SAL > 2500 AND DEPTNO = 20;`
## Lesson #7: Combining WHERE, AND, & OR with Operators
---
`SELECT * 
FROM EMP 
WHERE JOB = 'SALESMAN' 
OR JOB = 'CLERK';`

`SELECT ENAME 
FROM EMP
WHERE JOB != 'SALESMAN' AND JOB != 'MANAGERS'
AND SAL >= 2000;`
## Lesson #8: Query Filtering Continued BETWEEN, IN and NULL
---
`SELECT ENAME, HIREDATE
FROM EMP
WHERE DEPTNO IN (20,30);`
- IN is better to use where needing to use multiple OR clause
- NOT IN can be used to filter out values not needed
- BETWEEN operator filters based on a range of data
`SELECT * FROM EMP
WHERE HIREDATE BETWEEN '05/01/1981' AND '12/09/1982';`

`SELECT * FROM EMP
WHERE SAL BETWEEN 1000 AND 2000;`
- BETWEEN is inclusive
- NOT BETWEEN will not include the values used

`SELECT * FROM EMP WHERE COMM IS NULL;`
`SELECT * FROM EMP WHERE COMM IS NOT NULL;`
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

## Lesson 10: Ordering, Concatenating, and Aliasing Query Results
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
