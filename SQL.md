* [Топ-65 вопросов по SQL с собеседований, к которым вы должны подготовиться в 2019 году. Часть I](https://habr.com/ru/company/otus/blog/461067/)
* [Наш вариант теста на знание SQL](https://habr.com/ru/post/181033/)
* [Вотпросы и ответы 1](https://andreyex.ru/bazy-dannyx/uchebnoe-posobie-po-sql/14-naibolee-chasto-ispolzuemyx-zaprosov-sql-vopros-otvet/)
* [Вопросы и ответы 2](https://www.sql.ru/forum/1301998-2/zadachi-dlya-sql-dzhunov-s-otvetami)
* [Оконные функции](https://www.fastreport.ru/ru/blog/251/show/)


## Вопрос 1

в каких строках изменяется значения (по порядку)?
а лучше последняя и первая строка нового значения
```
id значение
----------
1 нет
2 да <-?
3 да
4 да <-?
5 нет
6 нет
7 да <-?
8 да
9 да
10 да
11 да <-?
12 нет
```

### Ответ 1

Если id — это число и оно точно-точно идет последовательно, то можно просто сделать join этой таблицы самой с собой по условию r.id = l.id + 1 ну и выбрать те строки где l.value <> r.value
Если же такое требование на id не выполняется, то можно пронумеровать через оконные функции и row_number() а дальше то же самое.

```sql
SELECT Id, v FROM #t

SELECT * FROM (
    SELECT Id, v, v1 = (SELECT TOP 1 v FROM #t t2 WHERE t2.Id > t1.Id ORDER BY ID) 
    FROM #t t1 
) AS t3
WHERE t3.v <> t3.v1
```

```sql
SELECT t1.*
FROM @t t1 LEFT JOIN @t t2 ON t1.id = t2.id + 1
WHERE t1.v <> t2.v
```

