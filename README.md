# Ansible Role - Install and configure MySQL

#### Variables

* mysql_backup_directory: Directory to save backups of mysql dumps to (default: /var/backups/db-dump)
* mysql_backup_delete_after: Days after which dumps will be deleted (default: 7)
* mysql_backup_minute: Minute when the cron will be executed which will create the dump (default: 11)
* mysql_backup_hour: Hour when the cron will be executed which will create the dump (default: 3)
* mysql_type: Choose between system (from distribution repository), vendor (from oracle mysql repository) or mariadb (from mariadb repository)

#### Special notes on mysqlbackup

You can specify custom compression arguments for sql files by creating a /etc/default/mysqlbackup file and overwriting the parameters:

```bash
COMPRESS="/PATH/TO/COMPRESSION/PROGRAM"
COMPRESS_ENDING="FILEENDING"
COMPRESS_PARAMS="-PARAMETERS -FOR -COMPRESSION -PROGRAM"
```

#### Known errors

If you are getting the following error message
```
{"changed": false, "failed": true, "msg": "(-1, 'error totally whack')"}
```

mysql/mariadb most likely didn't update it's table schema for the mysql database.

To fix this try:
```bash
mysql_upgrade
service mysql restart
```

