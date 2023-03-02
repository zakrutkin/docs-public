**TimescaleDB** — расширение PostgreSQL для работы с временными рядами, реализованными в виде гипертаблиц (`create_hypertable`).

Больше информации об использовании расширения можно найти на странице [документации расширения](https://docs.timescale.com/api/latest).

#### Параметры, применимые в инфраструктуре VK Cloud:

|Название| Описание                                                                                                                                           |Пример|
|---|----------------------------------------------------------------------------------------------------------------------------------------------------|---|
|`database`| Указывает, на каких базах данных будет развернуто расширение. Удаление баз данных из этого списка для установленного расширения не поддерживается. |`--database="timescale_DB"`|