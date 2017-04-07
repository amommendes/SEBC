# Hostname

```
[root@ip-10-0-1-203 ~]# hostname
ip-10-0-1-203
[root@ip-10-0-1-203 ~]# hostname -f
ip-10-0-1-203.sa-east-1.compute.internal
```

# DB Version

```
[root@ip-10-0-1-203 ~]# mysql --version
mysql  Ver 15.1 Distrib 10.1.22-MariaDB, for Linux (x86_64) using readline 5.1
```

# Databases created

```
[root@ip-10-0-1-203 ~]# mysql -uroot -p
Enter password: 
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 12
Server version: 10.1.22-MariaDB MariaDB Server

Copyright (c) 2000, 2016, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| amon               |
| hive               |
| hue                |
| information_schema |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)

``` 