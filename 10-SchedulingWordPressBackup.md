###How to get fullbackup(files+db) from wordpress###
**1. Script for generating a full backup of your wordpress site**

```
#!/bin/bash

# This script creates a compressed backup archive of the given directory and the given MySQL table.
# Author: mahdi mansoori exclusively for github.com/mansoorimahdi in April, 2023

# Set the date format, filename and the directories where your backup files will be placed and which directory will be archived.
NOW=$(date +"%Y-%m-%d-%H-%M")
FILE="files_$NOW.tar"
BACKUP_DIR="/var/backups/mahdimansoori.ir"
WWW_DIR="/var/www/html/wp_mahdimansoori"

# MySQL database credentials
DB_USER=""
DB_PASS=""
DB_NAME=""
DB_FILE="db_$NOW.sql"

# Tar transforms for better archive structure.
WWW_TRANSFORM='s,/var/www/html/wp_mahdimansoori,www,'
DB_TRANSFORM='s,/var/backups/mahdimansoori.ir,database,'

# Create the archive and the MySQL dump
tar -cvf $BACKUP_DIR/$FILE --transform $WWW_TRANSFORM  $WWW_DIR
mysqldump -u$DB_USER -p$DB_PASS $DB_NAME > $BACKUP_DIR/$DB_FILE

# Append the dump to the archive, remove the dump and compress the whole archive.
tar --append --file=$BACKUP_DIR/$FILE --transform $DB_TRANSFORM $BACKUP_DIR/$DB_FILE
rm $BACKUP_DIR/$DB_FILE
gzip -9 $BACKUP_DIR/$FILE

# Delete files older than 10 days #
find $BACKUP_DIR/*.gz -mtime +10 -exec rm {} \;
```

**2. rsync command to copy new backup from remote server to local system**
rsync -chavzP -e "ssh -p number" user@ServerOrIP.ir:/remote/path/to/copy/ /local/path/