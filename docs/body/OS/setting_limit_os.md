# Лимиты
Увеличение числа открытых файлов
Процессы PostgreSQL могут требовать большого количества открытых файлов, особенно при высокой нагрузке.

## Настройки в /etc/security/limits.conf:
postgres soft nofile 65536
postgres hard nofile 65536

Проверка текущих лимитов:
ulimit -n

Установка нового значения (например, в /etc/profile для постоянного применения):
ulimit -n 65536