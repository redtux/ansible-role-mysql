# Ansible Role - Install and configure MySQL

#### Variables

* mysql_server_package_debian: Which package use to install mysql server (default: mysql-server)
* mysql_client_package_debian: Which package use to install mysql client (default: mysql-client)
* mysql_backup_directory: Directory to save backups of mysql dumps to (default: /var/backups/db-dump)
* mysql_backup_delete_after: Days after which dumps will be deleted (default: 7)
* mysql_backup_minute: Minute when the cron will be executed which will create the dump (default: 11)
* mysql_backup_hour: Hour when the cron will be executed which will create the dump (default: 3)
* mysql_optimization_version: Choose 5 for mysql 5.5 or 6 for mysql 5.6 (default: 5)
