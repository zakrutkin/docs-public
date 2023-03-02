## MySQL 5.7

MySQL — свободная реляционная система управления базами данных. Разработку и поддержку MySQL осуществляет корпорация Oracle, получившая права на торговую марку вместе с поглощённой Sun Microsystems, которая ранее приобрела шведскую компанию MySQL AB. Разработчики создают функциональность по заказу лицензионных пользователей. Именно благодаря такому заказу почти в самых ранних версиях появился механизм репликации.

Входит в состав серверов WAMP, AppServ, LAMP и в портативные сборки серверов Денвер, XAMPP, VertrigoServ. Обычно MySQL используется в качестве сервера, к которому обращаются локальные или удалённые клиенты, однако в дистрибутив входит библиотека внутреннего сервера, позволяющая включать MySQL в автономные программы.

Гибкость СУБД MySQL обеспечивается поддержкой большого количества типов таблиц: пользователи могут выбрать как таблицы типа MyISAM, поддерживающие полнотекстовый поиск, так и таблицы InnoDB, поддерживающие транзакции на уровне отдельных записей. Более того, СУБД MySQL поставляется со специальным типом таблиц EXAMPLE, демонстрирующим принципы создания новых типов таблиц. Благодаря открытой архитектуре и GPL-лицензированию, в СУБД MySQL постоянно появляются новые типы таблиц.

Подробнее вы можете [прочесть в официальной документации](https://dev.mysql.com/doc/).

## MySQL 8.0

Главные обновления в версии 8.0:

- Улучшения словаря данных — теперь MySQL Server включает транзакционный словарь данных, который хранит информацию об объектах базы данных. Подробней об изменениях в словаре данных читайте [здесь](https://dev.mysql.com/doc/refman/8.0/en/data-dictionary.html).
- Улучшения JSON функционала — в 8 версии было много изменений, связанных с JSON в MySQL. Например, добавлен оператор `->>`, который является эквивалентом вызова `JSON_UNQUOTE()` на результате `JSON_EXTRACT()`. Функции аггрегирования `JSON_ARRAYAGG()` и `JSON_OBJECTAGG()`, добавлена возможность частичного обновления JSON колонки и использования диапазонов в XPath выражениях, функция `JSON_MERGE()` и много другое.
- Оптимизатор — добавлены невидимые и нисходящие индексы. Невидимые не используются оптимизатором, но позволяют протестировать изменение производительности от удаления индекса. И теперь при определении индекса ключ DESC больше не игнорируется, вместо этого индексы будут храниться в обратном порядке.
- Кодировка по умолчанию — в версии 8 стандартной кодировкой будет utf8mb4.
- Роли — появилась возможность создавать роли и закреплять за ними нужные привилегии. Например:

```
CREATE ROLE 'developer_role';
GRANT SELECT ON database.* TO 'developer_role';
GRANT 'developer_role' TO 'user'@'localhost';
```

Ознакомиться со всеми обновлениями можно на [официальном сайте](https://dev.mysql.com/doc/refman/8.0/en/mysql-nutshell.html).