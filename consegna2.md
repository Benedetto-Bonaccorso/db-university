group by

select count(`id`) as `students_this_year`, year(`enrolment_date`) as `year` from `students` group by `year`;

select count(`id`) as `offices_in_building`, `office_address` from `teachers` group by `office_address`;

select `exam_id`, avg(`vote`) as `average_in_exam` from `exam_student` group BY `exam_id`;

select `department_id` as 'department_id', count(id) as 'number_of_degrees' from `degrees` group by `department_id`;

join

select students.degree_id , students.name , `Corso di Laurea in Economia` from students inner join degrees on degrees.id = students.degree_id;

Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze XXXXX

select `courses`.`*` , `teachers`.`name`, `teachers`.`surname` from `course_teacher` join `courses` on `courses`.`id` = `course_teacher`.`course_id` join `teachers` on `teachers`.`id` = `course_teacher`.`teacher_id` where `teachers`.`id` = 44;

select `students`.`name` as 'student_name',`students`.`surname` as 'student_surname', `degrees`.`*` , `departments`.`name` as 'department_name' from `degrees` join `students` on `degrees`.`id` = `students`.`degree_id` join `departments` on `degrees`.`department_id` = `departments`.`id` order by `students`.`surname` asc, `students`.`name` asc;

select  `degrees`.`*`, `teachers`.`name` as 'teacher_name', `teachers`.`surname` as 'teacher_surname', `courses`.`name` as 'course_name' from `course_teacher` join `teachers` on `teachers`.`id` = `course_teacher`.`teacher_id` JOIN `courses` on `course_teacher`.`course_id` = `courses`.`id` join `degrees` on `degrees`.`id` = `courses`.`degree_id`;

select distinct `teachers`.`*`, `departments`.`name` as 'department_name' from `course_teacher` join `teachers` on `teachers`.`id` = `course_teacher`.`teacher_id` join `courses` on `course_teacher`.`course_id` = `courses`.`id` join `degrees` on `degrees`.`id` = `courses`.`degree_id` join `departments` on `degrees`.`department_id` = `departments`.`id` where `departments`.`name` = 'Dipartimento di Matematica';