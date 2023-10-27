# update
Обновление данных.

В таблице `countries` вставляем в столбец `name` слово `Империя` вместо `Россия` в строке с `id = 1`:

    UPDATE `countries` SET `name` = 'Империя' WHERE `countries`.`id` = 1;
