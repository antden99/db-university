Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

- SELECT `degrees`.`name`,`students`.`name`,`students`.`surname` FROM `degrees` JOIN `students` ON `degrees`.`id` = `students`.`degree_id` WHERE `degrees`.`name`= "Corso di Laurea in Economia";
  (total 68)

Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

- SELECT `departments`.`id` AS `departments_id`, `departments`.`name`, `departments`.`address`,
  `degrees`.`id` AS `degrees_id`, `degrees`.`name`
  FROM `departments`
  JOIN `degrees` ON `departments`.`id` = `degrees`.`department_id`
  WHERE `degrees`.`level` = "magistrale" AND `departments`.`name` = "Dipartimento di Neuroscienze";
(total 1)


Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
- SELECT * FROM `teachers` JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id` JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id` WHERE `teachers`.`id` = 44;
(total 11)

Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

- SELECT `students`. `name`,`students`.`surname`,`degrees`.`name`,`degrees`.`level`,`departments`.`name`
FROM `students`
JOIN `degrees` ON `students`.`degree_id`= `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname`, `students`.`name`;

Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

-SELECT `degrees`.`name`,`degrees`.`level`,`courses`.`name` AS NameOfCourses, `courses`.`period`,`teachers`.`name` AS NameOfTeacher, `teachers`.`surname` AS SurnameOfTeacher
FROM `degrees`
JOIN `courses` ON `degrees`.`id`= `courses`.`degree_id`
JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `teachers` ON `course_teacher`.`teacher_id`=`teachers`.`id`;

Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

- SELECT DISTINCT `teachers`.`id`, `teachers`.`name`, `teachers`.`surname`
FROM `teachers`
JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id`
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = "Dipartimento di Matematica";

BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

-
