1 - Contare quanti iscritti ci sono stati ogni anno
- SELECT COUNT(`id`),YEAR(`enrolment_date`) FROM `students` GROUP BY YEAR(`enrolment_date`);
- (4 total)

2 - Contare gli insegnanti che hanno l'ufficio nello stesso edificio
- SELECT COUNT(`id`),office_number FROM `teachers` GROUP BY `office_number`;
- (74 total)

3 - Calcolare la media dei voti di ogni appello d'esame
- SELECT `exam_id`, AVG(`vote`) FROM `exam_student` GROUP BY `exam_id`;
- ( 4078 total)

4 - Contare quanti corsi di laurea ci sono per ogni dipartimento
- SELECT COUNT(`id`),`department_id` FROM `degrees` GROUP BY `department_id`;
- (12 total)


