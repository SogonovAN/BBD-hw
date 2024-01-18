# Домашнее задание к занятию "Резервное копирование баз данных - `Согонов Алексей`"

### Задание 1

```

1.1.Можно использовать полный бэкап раз в неделею и дифференциальный каждый день это более надежный вид бэкапа, который позволит восстановить данные в за любой день недели.
1.2.Можно использовать полный бэкап раз в неделю и инкрементный каждый час, данная схема позволит снизить место для хранения бэкапов и даст больше количество точек восстановления.


```

### Задание 2

```

pg_dump dbname > dumpfile - создать резервную копию БД.
psql dbname < dumpfile - восстановить БД.

```

### Задание 3

```

Создание инкрементного бэкапа:
mysqlbackup --defaults-file=/home/dbadmin/my.cnf \
  --incremental=optimistic --incremental-base=history:last_backup \
  --backup-dir=/home/dbadmin/temp_dir \
  --backup-image=incremental_image1.bi 
   backup-to-image

Восстановление бэкапа:
mysqlbackup --defaults-file=<my.cnf> -uroot --backup-image=<inc_image_name> \
  --backup-dir=<incBackupTmpDir> --datadir=<restoreDir> --incremental \
  copy-back-and-apply-log

```

---
