# pg_upgrade в PostgreSQL
pg_upgrade — это утилита командной строки в PostgreSQL, которая предназначена для обновления версии PostgreSQL, позволяя перенести данные и настройки из старого кластера в новый. Эта утилита помогает администраторам баз данных обновлять PostgreSQL на новые версии без необходимости создания новой базы данных и импорта данных.

!!! info "Основное назначение"
    pg_upgrade используется для обновления версии PostgreSQL на новые версии без потери данных и настроек. Основные цели использования этой утилиты включают в себя:

Обновление версии PostgreSQL: pg_upgrade позволяет администраторам баз данных безопасно обновлять PostgreSQL на новые версии без необходимости создания новой базы данных и импорта данных.

Перенос данных и настроек: Утилита переносит данные и конфигурационные файлы из старого кластера PostgreSQL в новый, обеспечивая сохранность данных и сохранение настроек.

## Синтаксис команды
pg_upgrade [option...]

Опции
Некоторые наиболее часто используемые опции pg_upgrade:

-b oldbindir, --old-bindir=oldbindir
Устанавливает путь к каталогу bin (binaries) старой версии PostgreSQL.

-B newbindir, --new-bindir=newbindir
Устанавливает путь к каталогу bin (binaries) новой версии PostgreSQL.

-d olddatadir, --old-datadir=olddatadir
Устанавливает путь к каталогу данных (datadir) старого кластера PostgreSQL.

-D newdatadir, --new-datadir=newdatadir
Устанавливает путь к каталогу данных (datadir) нового кластера PostgreSQL.

## Примеры использования
Обновление версии PostgreSQL с использованием опций по умолчанию
pg_upgrade -b /path/to/old/bin -B /path/to/new/bin -d /path/to/old/data -D /path/to/new/data

Обновление версии PostgreSQL с пользовательскими опциями
pg_upgrade -b /path/to/old/bin -B /path/to/new/bin -d /path/to/old/data -D /path/to/new/data --check --link

## Полезные советы
Резервное копирование данных: Перед выполнением обновления версии PostgreSQL убедитесь, что у вас есть резервная копия данных для восстановления в случае необходимости.
Проверка перед обновлением: Выполните предварительную проверку с помощью pg_upgrade --check, чтобы убедиться, что данные и настройки готовы к обновлению.

## Полезные ссылки
Документация по pg_upgrade
https://www.postgresql.org/docs/current/pgupgrade.html
pg_upgrade является важным инструментом для обновления версии PostgreSQL на новые версии без необходимости создания новой базы данных и импорта данных. Правильное использование этой утилиты помогает обеспечить безопасное и эффективное обновление базы данных PostgreSQL.