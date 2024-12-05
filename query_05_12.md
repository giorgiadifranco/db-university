````sql
-- 1 Contare quanti iscritti ci sono stati ogni anno

SELECT YEAR(enrolment_date) AS year, COUNT(*) AS total_enrollments
FROM students
GROUP BY year

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


-- 5 Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SELECT students.id, students.name, degrees.id, degrees.name
FROM students
JOIN degrees
ON students.degree_id = degrees.id
WHERE degrees.name = 'Corso di Laurea in Economia';
```sql
````
