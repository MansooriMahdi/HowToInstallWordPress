**1. how to set a permission to append only?**
```
chattr +a filename.txt
```
**2. Nobody can modify or delete a file(immutable)**
```
chattr +i filename.txt
```
**3 Cronjobs**
**3.1 Runing a task at first minute of first day of week**
```
1 0 * * 0 df -h >> /opt/diskusage`date "+\%Y-\%m-\%d-\%H-\%M"`.txt
```
**3.2 At every reboot copy log file and send as mail**
```
 @reboot gzip -c /var/log/syslog | uuencode log.gz | mail -s "log file for `date`" mahdi@umac

```