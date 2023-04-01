###How to Dumping my database with cron jobs
**1. Define backup command:**
```
mysqldump -u db_user -p db_password db_name
```

**2. Compressing dump result:**
```
mysqldump -u db_user -p db_password db_name | gzip > /backup_path/db_$(date +\%Y-\%m-\%d).sql.gz
```

**3. Add to Cronjobs:**
Run crontab command with e swith for editing:
```
crontab -e
```
Add below line for dumping sql db in 2:0 at every day
```
0 2 * * * mysqldump -u db_user -p db_password db_name | gzip > /backup_path/db_$(date +\%Y-\%m-\%d).sql.gz
```