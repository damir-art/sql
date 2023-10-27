# inner join
Выташим из таблицы заголовки из другой таблицы привязанные к внешнему ключу. Например из таблицы cointries, вытащим названия континентов.

Оператор `join` склеивает таблицы при запросе, сопоставляет цифры из `continent_id` в таблице `contries` и названия континентов из таблицы `continents`.

    SELECT world.continents.name
    FROM world.countries
    INNER JOIN world.continents
    ON world.countries.continent_id = world.continents.id;
