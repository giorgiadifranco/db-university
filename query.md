## 1

SELECT \*
FROM students
where YEAR (date_of_birth) = 1990;

## 2

SELECT \*
FROM courses
where cfu > 10;

## 3

SELECT \*
FROM students
WHERE TIMESTAMPDIFF(YEAR, date_of_birth, CURDATE()) > 30

## 4

SELECT \*
FROM courses
WHERE period= 'II semestre' AND year= 1;

## 5

SELECT \*
FROM exams
where hour > '14:00:00'
