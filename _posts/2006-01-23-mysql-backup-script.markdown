---
layout: post
title: "MySQL Backup Script"
Slug: mysql-backup-script
date: 2006-01-23 01:07:49
tags: [Hosting,Open Source,Uncategorized,Work Life]
---
There are oh-so-many of these on the web, so I thought I'd add another. I got inspirations from [two](http://blogs.linux.ie/xeer/2005/06/28/simple-mysql-backup/) [sources](http://bash.cyberciti.biz/backup/mysql-backup.bash.php), and here's my version.

```
#!/bin/bash
# MYSQL Backup Script
#
# Creates:
# $BACKUP_PATH/
# '-- yyyy-mm-dd/
#   |-- database_name.sql       Full database backup
#   `-- database_name/
#     |-- table1.sql            Individual database table backup
#     |-- table2.sql            Individual database table backup
#     |-- table3.sql            Individual database table backup
#     `-- table4.sql            Individual database table backup

<p>###########################
# CONFIG
########
MYSQL="$(which mysql)"
MYSQLDUMP="$(which mysqldump)"
CHOWN="$(which chown)"
CHMOD="$(which chmod)"
TAR="$(which tar)"
DATE=$(date +"%Y-%m-%d")
BACKUP_PATH="/var/backups/mysql"

</p><p>#Create database dump directory and go there
mkdir -p $BACKUP_PATH/$DATE
pushd $BACKUP_PATH >> /dev/null

</p><p># Loop through each database
for database in `echo "show databases" | $MYSQL | grep -v Database`;
do
        mkdir -p $DATE/$database

</p><p>
# Dump database
        $MYSQLDUMP --defaults-file=/root/.my.cnf --add-drop-table --allow-keywords -a -a -c $database

>$DATE/$database.sql

</p><p>
# Loop through each table
        for table in `echo "use $database; show tables" | $MYSQL $database | grep -v Tables_in_`;
        do

</p><p>
# Dumping table
                $MYSQLDUMP --defaults-file=/root/.my.cnf --add-drop-table --allow-keywords -q -a -c $database $table

>$DATE/$database/$table.sql

</p><p>        done

</p><p>done

</p><p># Create daily archive
$TAR jcf $DATE.tar.bz $DATE

</p><p># Ensure only root can access these files
$CHOWN 0.0 -R $DATE
$CHOWN 0.0 $DATE.tar.bz
$CHMOD go-rwx $DATE
$CHMOD go-rwx $DATE.tar.bz
$CHMOD go-rwx -R $DATE/*

</p><p># Back to start directory
popd >> /dev/null</p>
```

I was going to go to the extent of using `which` to find the location of grep and echo, but thought it unnecessary. Makes me wonder, should we use `which` to find which??
