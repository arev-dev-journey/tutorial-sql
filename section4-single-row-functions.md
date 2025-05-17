# Single Row Functions
---
## Lesson # 11: Single Row Functions (SRF) & Using The Dual Table
---
`SELECT Concat('My name is ', ename) as sentence
FROM emp;`

`SELECT upper('Hello')
FROM emp;`

`SELECT lower('hello')
FROM dual;`

SELECT * FROM dual;

`SELECT 'pizza' as FOOD, 'fanta' as DRINK, concat('hello', 'alex') as "This is a func" FROM dual;`
