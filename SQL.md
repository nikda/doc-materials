* [Топ-65 вопросов по SQL с собеседований, к которым вы должны подготовиться в 2019 году. Часть I](https://habr.com/ru/company/otus/blog/461067/)
* [Наш вариант теста на знание SQL](https://habr.com/ru/post/181033/)
* [Вотпросы и ответы 1](https://andreyex.ru/bazy-dannyx/uchebnoe-posobie-po-sql/14-naibolee-chasto-ispolzuemyx-zaprosov-sql-vopros-otvet/)
* [Вопросы и ответы 2](https://www.sql.ru/forum/1301998-2/zadachi-dlya-sql-dzhunov-s-otvetami)
* [Оконные функции](https://www.fastreport.ru/ru/blog/251/show/)
* [Типы физических соединений](http://sql-ex.ru/blogs/optimization/merge-joins.html)
* [Графический план выполнения запросов SQL Server в действии](http://www.sqlbooks.ru/readarticle.aspx?part=02&file=tuningperf13)
* [Графическое изображение плана исполнения, выдаваемого SQL Query Analyzer](http://www.softpoint.ru/archive/article_id17.php)
* [Задание с примером](http://www.cyberforum.ru/sql-server/thread1544839.html)
* [Storing passwords in a secure way (HASH)](https://www.mssqltips.com/sqlservertip/4037/storing-passwords-in-a-secure-way-in-a-sql-server-database/)
* [На пути к правильным SQL транзакциям (Часть 1)](https://habr.com/ru/company/infopulse/blog/261097/)
* [На пути к правильным SQL транзакциям (Часть 2)](https://habr.com/ru/company/infopulse/blog/261101/)
* [Оптимизация производительности SQL Server с использованием индексов](https://habr.com/ru/post/164717/)
* [14 вопросов об индексах в SQL Server, которые вы стеснялись задать](https://habr.com/ru/post/247373/)
* [Индексы](https://www.sql.ru/articles/mssql/03013101indexes.shtml)
* [Разгребание очереди](https://www.sql.ru/forum/254557/a-est-li-smysl-with-updlock-holdlock-readpast)
```
Комбинация WITH(UPDLOCK, READPAST) - совершенно классическое решение для разгребания очереди. Допустим у нас есть таблица с несколькими записями у которых IsProcessed=0 и которые надо обработать каким-то образом из параллельных потоков. Запрос
SELECT TOP 1 * FROM ... WITH(UPDLOCK, READPAST) WHERE IsProcessed=0
из нескольких потоков приведет к тому, что каждый поток получит свою запись с IsProcessed=0 незаблокированную чужими потоками и с гарантией, что ее никто не запросит, пока с ней возятся в транзакции.
После этого в той же транзакции идет обработка этой записи и выставление IsProcessed=1. Думаю идея ясна...
HOLDLOCK приведет к тому, что будет удерживаться блокировка не на одной записи, а на диапазоне ключей индекса (если индекс найдется подходящий). Что будет препятствовать вставке новой записи с этим ключем в таблицу, даже если на момент выборки такой записи не существовало вовсе... И сдается мне, что это лишнее.
```

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

