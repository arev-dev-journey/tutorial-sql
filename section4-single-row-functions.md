# Single Row Functions
---
## Lesson #11: Single Row Functions (SRF) & Using The Dual Table
---
`SELECT 'my name is ' || ename
FROM emp;`

`SELECT concat('My name is ', ename) as sentence
FROM emp;`

`SELECT upper('Hello')
FROM emp;`

`SELECT lower('hello')
FROM dual;`

`SELECT * FROM dual;`

`SELECT 'pizza' as FOOD, 'fanta' as DRINK, concat('hello', 'alex') as "This is a func" FROM dual;`

`SELECT lower(ename) FROM emp;`
`SELECT concat(lower(ename), upper(' is the name')) FROM emp
WHERE deptno = 20;`

-- Solution to Assignment
`SELECT concat(concat(lower(ename), upper(' is the name')), concat(' and their job is: ', job)) as "function call"
FROM emp
WHERE deptno = 20;`

## Lesson #12: Using Functions in WHERE And Character-Based SRFs
---
`SELECT lower(ename) FROM emp;` `SELECT * FROM emp WHERE job = upper('manager');`

`SELECT initcap('Hello, my name is Alex') AS sentence
FROM dual;`

`SELECT length('hello, my name is Alex') AS length
FROM dual;`

`SELECT length(ename) AS length
FROM emp;`

`SELECT ename, length(ename) AS length
FROM emp
WHERE length(ename) = 6;`

`SELECT substr('hello', 2, 2)
FROM dual;`

`SELECT LPAD('hello',10,'&')
FROM dual;`

`SELECT RPAD(10,1,'$')
FROM dual;`

`SELECT RTRIM('hhhhheellllooohhhh','h')
FROM dual;`

## Lesson #13: Numeric and Date Data type SRFs
---
`SELECT round(107.89342) FROM dual;`
`SELECT round(107.2123, 2) FROM dual;`
`SELECT trunc(107.99999) FROM dual; // Output: 107`
`SELECT trunc(107.99999,2) FROM dual;   // Output: 107.99`

`SELECT systimestamp FROM dual;`
`SELECT add_months('11/17/2012',8) FROM dual;`
`SELECT months_between('01/01/2021', '01/01/2022') FROM dual;`
`SELECT trunc(systimestamp) FROM dual`;
-- Can take month or year as a second argument
## Lesson #14: Conversion SRFs and Date Formatting
---
