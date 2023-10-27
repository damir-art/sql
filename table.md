# Таблица
Работа с таблцей.

## Создание таблицы
https://metanit.com/sql/mysql/2.1.php  
Имя таблицы долно иметь множественное число.

Переходим в БД > Название таблицы:
- имя таблицы `countries`

Создание столбцов таблицы:  
https://metanit.com/sql/mysql/2.2.php  

`id`:
- тип: int
- атрибуты: unsigned
- индекс: primary
- a_i: галочка
`name`:
- тип: varchar
- длина/значения: 255
`capital`:
- тип: varchar
- длина/значения: 255
`people`:
- тип: int

Код:

    CREATE TABLE `world`.`countries` (
      `id` INT NOT NULL AUTO_INCREMENT ,
      `name` VARCHAR(255) NOT NULL ,
      `capital` VARCHAR(255) NOT NULL ,
      `people` INT NOT NULL ,
      PRIMARY KEY (`id`)) ENGINE = InnoDB;

После создания столбцов их можно потом редактировать.

## Переименование таблицы

    RENAME TABLE `table_name` TO `new_table_name`;
