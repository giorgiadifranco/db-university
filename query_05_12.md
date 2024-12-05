````sql
-- Contare quanti iscritti ci sono stati ogni anno

SELECT YEAR(enrolment_date) AS year, COUNT(*) AS total_enrollments
FROM students
GROUP BY year

 -- Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT office_address AS same_address, COUNT(*) AS teachers
From teachers
Group by office_address

-- Calcolare la media dei voti di ogni appello d'esame
SELECT exam_id, AVG(vote) as vote_avarage
FROM exam_student
group by exam_id
order by exam_id

-- Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT department_id, COUNT(name)
FROM degrees
group by department_id
```sql
````
