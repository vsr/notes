# Unix commands

#### Directory size
```
du -sh directory_name
```

#### Mount drive
Edit /etc/fstab and then run
````
mount -a
````

#### MD5 checksum for files
````
md5sum directory/* > md5.txt
````

#### Processes sorted by memory used
````
ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%mem | head
````
