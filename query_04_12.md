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

````sql
SELECT COUNT('id') as teachers_no_phone
from teachers
where phone is null
```sql
````

````sql
## 9
insert into students('degree_id','name', 'surame','date_of_birt','fiscal_code','enrolment_date','registration_number', 'email')
VALUE (61, 'nicola', 'ambrosini','1990-08-4','kjhfkjskjbgkjgkgjkjh', '20-03-2022', '68798573985','nico.ambro@hjkhfj.it')

SELECT *
FROM students
WHERE 'registration_number'= 123456
```sql

## 10
```sql
SELECT *
FROM teachers
where surname = 'rizzo'
```sql

````
