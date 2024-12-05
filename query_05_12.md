````sql
-- 1 Contare quanti iscritti ci sono stati ogni anno

SELECT YEAR(enrolment_date) AS year, COUNT(*) AS total_enrollments
FROM students
GROUP BY YEAR (enrolment_date)

 -- 2 Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT office_address AS same_address, COUNT(*) AS teachers
From teachers
Group by office_address

-- 3 Calcolare la media dei voti di ogni appello d'esame
SELECT exam_id, AVG(vote) as vote_avarage
FROM exam_student
group by exam_id
order by exam_id

-- 4 Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT department_id, COUNT(name)
FROM degrees
group by department_id


```JOINS
```

-- 1 Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SELECT students.id, students.name, degrees.id, degrees.name
FROM students
JOIN degrees
ON students.degree_id = degrees.id
WHERE degrees.name = 'Corso di Laurea in Economia';

-- 2 Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
SELECT degrees.id AS degree_id, degrees.name AS degree_name, departments.name AS department_name
FROM degrees
JOIN departments
ON degrees.department_id = departments.id
WHERE degrees.level = 'Magistrale'
AND departments.name = 'Dipartimento di Neuroscienze';

-- 3 Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
SELECT teachers.name, teachers.surname, teachers.id, courses.id, courses.name
FROM teachers
JOIN course_teacher ON teachers.id = course_teacher.teacher_id
JOIN courses ON course_teacher.course_id = courses.id

WHERE teachers.id = 44

-- 4 Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
SELECT students.name, students.surname, students.id AS student_id, degrees.name, degrees.id AS degree_id, department_id, departments.name
FROM students
JOIN degrees on students.degree_id = degrees.id
JOIN departments on degrees.department_id = departments.id
ORDER BY students.surname and students.name

-- 5 Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
SELECT courses.name AS course_name, courses.id AS course_id, degrees.name AS degree_name, degrees.id AS degree_id, teachers.name AS teacher_name, teachers.surname AS teacher_surname, teachers.id AS teacher_id
FROM courses
JOIN course_teacher ON courses.id = course_teacher.course_id
JOIN teachers ON course_teacher.teacher_id = teachers.id
JOIN degrees ON courses.degree_id = degrees.id;

-- 6 Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
SELECT DISTINCT teachers.id AS teacher_id, teachers.name AS teacher_name, teachers.surname AS teacher_surname
FROM teachers
JOIN course_teacher ON teachers.id = course_teacher.teacher_id
JOIN courses ON course_teacher.course_id = courses.id
JOIN degrees ON courses.degree_id = degrees.id
JOIN departments ON degrees.department_id = departments.id
WHERE departments.name = 'Dipartimento di Matematica';
```sql
````
