1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT
	`students`.*,
    `degrees`.`name` AS `degree_name`
FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'
;
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```sql
SELECT
	`departments`.`name` AS `department_name`,
    `degrees`.*
FROM `departments`
INNER JOIN `degrees`
ON `degrees`.`department_id` = `departments`.`id`
WHERE `department_id` = 7
AND `degrees`.`level` = 'magistrale'
;
```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT
	`courses`.*,
	`course_teacher`.*
FROM `courses`
INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`teacher_id`
WHERE `teacher_id` = 44
;
```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql
SELECT
	`students`.`surname`,
	`students`.`name`,
	`degrees`.`name` AS `degree_name`,
    `departments`.`name` AS `department_name`
FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `surname`
;
```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
SELECT
	`degrees`.`name` AS `degree_name`,
    `courses`.*,
    `teachers`.`name` AS `teacher_name`
FROM `degrees`
INNER JOIN `courses`
ON `courses`.`degree_id` = `degrees`.`id`
INNER JOIN `teachers`
ON `teachers`.`id` = `courses`.`id`
;
```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql

```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
   per ogni esame, stampando anche il voto massimo. Successivamente,
   filtrare i tentativi con voto minimo 18.

```sql

```
