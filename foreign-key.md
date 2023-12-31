# foreign key
Внешний ключ.

Например каждая страна находится на конкретном континенте, в одной таблице в столбце континент может быть множество повторов континентов, потому что на каждом континенте может располагаться множество стран.

Создаём таблицу континенты и в таблице Страны в столбец Континенты вписываем идентификаторы континентов из таблицы Континенты (также отдельная таблица может быть у категорий, тегов и т.п.).

- Это позволит избежать ошибок при добавлении повторяющихся данных,
- При заполнении таблицы `Страны`, в столбце континенты появится возможность выбрать из тех континентов которые есть в таблице `Континенты`.

При связывынии столбцов в `continent_id` в качестве значений должны быть числа.

Переходим в таблицу `Страны`:
- переименовываем столбец `continent` в `continent_id`
- тип данных столбца `continent_id` меняем на `int`
- размер и параметры такие же как и у id в таблице континентов
  - например int(11) unsigned (not null по желанию, автоинкремент не ставим)
- в таблице `страны` переходим в Структура > Связи
  - в поле ограничения внешнего ключа пишем имя внешнего ключа `continent_key`
  - столбец `continent_id`
  - таблица `continents`
  - сохранить

В структуре таблицы `contries` у солбца `continent_id` появится ключ индекс.

При попытке удаления/обновления какого-нибудь континента в таблице `continent` появится ошибка, если к нему привязаны какие-либо страны в таблице `contries` (restrict):
on delete/on update:
- cascade - удалить/обновить строку и связанные с ней
- set null - при удалении/обновлении строк связанные с ней ячейки в другой таблице станут NULL
- no action
- restrict - нельзя удалить/обновить строку если есть связь с другой таблицей
