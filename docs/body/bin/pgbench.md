# pgbench в PostgreSQL
pgbench — это утилита командной строки PostgreSQL, используемая для выполнения тестов производительности базы данных. Она может выполнять стандартные тесты или пользовательские сценарии, помогая оценить производительность вашей системы.

!!! info "Основное назначение"
    pgbench используется для оценки производительности системы PostgreSQL. Она выполняет набор стандартных транзакций, чтобы измерить, насколько эффективно база данных обрабатывает запросы при разных нагрузках.

Синтаксис команды
pgbench [OPTIONS] [DBNAME]

## Основные параметры

-i, --initialize
Инициализация тестовой базы данных (создание таблиц и начальная загрузка данных).

-s, --scale=NUM
Масштаб тестовой базы данных. Этот параметр указывает, сколько строк данных будет загружено.

-c, --client=NUM
Количество клиентских соединений (потоков), используемых в тесте.

-j, --jobs=NUM
Количество рабочих потоков, которые будут запускать клиентские соединения.

-T, --time=NUM
Время выполнения теста в секундах.

-t, --transactions=NUM
Количество транзакций, которые каждый клиент выполнит.

-r, --report-latencies
Показать латентность выполнения каждой транзакции.

-l, --log
Записывать результаты выполнения теста в лог-файл.

-h, --host=HOSTNAME
Хост, на котором работает сервер базы данных.

-p, --port=PORT
Порт, на котором сервер базы данных принимает соединения.

-U, --username=USERNAME
Имя пользователя для подключения к серверу базы данных.

-W, --password
Запрашивать пароль перед подключением.

-?, --help
Показать справку по использованию команды.

## Примеры использования
Инициализация тестовой базы данных

pgbench -i -s 10 mydatabase
Эта команда инициализирует тестовую базу данных mydatabase с масштабом 10, создавая необходимые таблицы и загружая данные.

Выполнение теста производительности с 10 клиентскими соединениями и 2 рабочими потоками в течение 60 секунд
pgbench -c 10 -j 2 -T 60 mydatabase
Эта команда запускает тест производительности на базе данных mydatabase, используя 10 клиентских соединений и 2 рабочих потока в течение 60 секунд.

Запуск теста производительности с записью латентности каждой транзакции
pgbench -c 10 -j 2 -T 60 -r mydatabase
Эта команда выполняет тест, аналогичный предыдущему, но также записывает латентность каждой транзакции.

Запуск теста производительности с записью результатов в лог-файл
pgbench -c 10 -j 2 -T 60 -l mydatabase
Эта команда выполняет тест и записывает результаты выполнения в лог-файл.

## Полезные советы
Инициализация базы данных: Перед выполнением теста производительности обязательно инициализируйте базу данных с параметром -i, чтобы создать и загрузить необходимые данные.
Параметры клиентских соединений и рабочих потоков: Подберите оптимальные значения для параметров -c и -j, чтобы максимально использовать ресурсы вашей системы.
Анализ результатов: Используйте параметры -r и -l для получения подробной информации о латентности транзакций и записи результатов в лог-файл для последующего анализа.
Масштабирование тестовой базы данных: Увеличивайте масштаб базы данных с помощью параметра -s, чтобы симулировать работу с большими объемами данных.

## Полезные ссылки
Документация по pgbench
https://www.postgresql.org/docs/current/pgbench.html
Тестирование производительности в PostgreSQL
https://www.postgresql.org/docs/current/benchmarking.html
pgbench является мощным инструментом для оценки производительности базы данных PostgreSQL, предоставляя гибкие возможности для настройки и проведения тестов, которые помогут выявить узкие места и оптимизировать производительность системы.
