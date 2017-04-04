# Installation and Replication Lab

## Installation

- Add MariaDB 10 repo and install it

``` 
sudo vi /etc/yum.repos.d/MariaDB.repo

[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.1/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1


sudo yum install MariaDB-server MariaDB-client

```

- my.cnf file from Master:

```
	

```

- Grants for slave user:


```
MariaDB [(none)]> show grants for 'slave'@'%' ;

| Grants for slave@%                                      |
|---------------------------------------------------------|
| GRANT REPLICATION SLAVE ON *.* TO 'slave'@'%' IDENTIFIED BY PASSWORD 'XXXX' |
```

- Master Status:

```

MariaDB [(none)]> SHOW MASTER STATUS;
+-------------------------+----------+--------------+------------------+
| File                    | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+-------------------------+----------+--------------+------------------+
| mysql_binary_log.000007 |     1953 |              |                  |
+-------------------------+----------+--------------+------------------+
1 row in set (0.00 sec)

```

- Slave configurations:

* Testing connection between slave and master (is necessary allow port 3306 to instance)


```
mysql -h10.0.1.122 -uslave -pXXX

```

* Starting slave

```
mysql -uroot -p

CHANGE MASTER TO
MASTER_HOST='10.0.1.122',
MASTER_USER='slave',
MASTER_PASSWORD='root',
MASTER_PORT=3306,
MASTER_LOG_FILE='mysql_binary_log.000007',
MASTER_LOG_POS=1953,
MASTER_CONNECT_RETRY=10,
MASTER_USE_GTID=current_pos;

MariaDB [(none)]> start slave;
Query OK, 0 rows affected (0.01 sec)

MariaDB [(none)]> show slave status\G
		Slave_IO_State: Waiting to reconnect after a failed master event read
		Master_Host: 10.0.1.122
		Master_User: slave
		Master_Port: 3306
		Connect_Retry: 10
		Master_Log_File: mysql_binary_log.000007
		Read_Master_Log_Pos: 1953
```

