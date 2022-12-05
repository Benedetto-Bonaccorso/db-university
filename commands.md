C:\MAMP\bin\mysql\bin\mysql -u root -p -P 3306 => root (password)

use `university`

select * from `students` where date_of_birth like '1990%';

select * from `courses` where cfu > 10;

select * from `students` where date_of_birth like '1992%'; (soluzione temporanea perchè non riesco a calcolare l'età dinamicamente) 

select * from `courses` where year = 1 and period = 'I semestre';

select * from `exams` where `date` = '2020-06-20' and hour >= '12:20:00';

select * from `degrees` where `level` = 'magistrale';

select count(0) from `departments`;

Quanti sono gli insegnanti che non hanno un numero di telefono? (50) HHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHH