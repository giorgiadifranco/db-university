## 1

````sql
SELECT *
FROM students
where YEAR (date_of_birth) = 1990;
```sql

## 2
```sql
SELECT *
FROM courses
where cfu > 10;
```sql

## 3
```sql
SELECT *
FROM students
WHERE TIMESTAMPDIFF(YEAR, date_of_birth, CURDATE()) > 30
```sql

## 4
```sql
SELECT *
FROM courses
WHERE period= 'I semestre' AND year= 1;
```sql

## 5
```sql
SELECT *
FROM exams
where hour > '14:00:00' AND date ='2020-06-26'
```sql
## 6

```sql
SELECT *
FROM degrees
WHERE level = 'magistrale'
```sql

## 7
```sql
SELECT COUNT('id') AS'total_departments'
FROM departments
```sql
````

## 8

```sql

```
