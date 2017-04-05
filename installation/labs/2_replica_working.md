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
MariaDB [(none)]> CREATE USER 'slave'@'%' IDENTIFIED BY 'slave';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> grant replication slave on *.* to 'slave'@'%' identified by 'slave' with grant option; 
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> flush privileges;
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> flush tables with read lock;
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> show master status;
+-------------------------+----------+--------------+------------------+
| File                    | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+-------------------------+----------+--------------+------------------+
| mysql_binary_log.000001 |     5093 |              |                  |
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
MASTER_HOST='10.0.1.19',
MASTER_USER='slave',
MASTER_PASSWORD='slave',
MASTER_PORT=3306,
MASTER_LOG_FILE='mysql_binary_log.000001',
MASTER_LOG_POS=5093,
MASTER_CONNECT_RETRY=10,
MASTER_USE_GTID=current_pos;

MariaDB [(none)]> start slave;
Query OK, 0 rows affected (0.01 sec)

MariaDB [(none)]> start slave;
Query OK, 0 rows affected (0.01 sec)

MariaDB [(none)]> show slave status\G
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: 10.0.1.19
                  Master_User: slave
                  Master_Port: 3306
                Connect_Retry: 10
              Master_Log_File: mysql_binary_log.000001
          Read_Master_Log_Pos: 5093
               Relay_Log_File: ip-10-0-1-37-relay-bin.000002
                Relay_Log_Pos: 5388
        Relay_Master_Log_File: mysql_binary_log.000001
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB: 
          Replicate_Ignore_DB: 
           Replicate_Do_Table: 
       Replicate_Ignore_Table: 
      Replicate_Wild_Do_Table: 
  Replicate_Wild_Ignore_Table: 
                   Last_Errno: 0
                   Last_Error: 
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 5093
              Relay_Log_Space: 5693
              Until_Condition: None
               Until_Log_File: 
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File: 
           Master_SSL_CA_Path: 
              Master_SSL_Cert: 
            Master_SSL_Cipher: 
               Master_SSL_Key: 
        Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error: 
               Last_SQL_Errno: 0
               Last_SQL_Error: 
  Replicate_Ignore_Server_Ids: 
             Master_Server_Id: 1
               Master_SSL_Crl: 
           Master_SSL_Crlpath: 
                   Using_Gtid: Current_Pos
                  Gtid_IO_Pos: 0-1-33
      Replicate_Do_Domain_Ids: 
  Replicate_Ignore_Domain_Ids: 
                Parallel_Mode: conservative
1 row in set (0.01 sec)

```


- Preparing MariaDB to Cloudera Manager Server 

```
create database amon DEFAULT CHARACTER SET utf8;
grant all on amon.* TO 'amon'@'%' IDENTIFIED BY 'amon';

create database rman DEFAULT CHARACTER SET utf8;
grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman';

create database metastore DEFAULT CHARACTER SET utf8;
grant all on metastore.* TO 'metastore'@'%' IDENTIFIED BY 'metastore';

create database sentry DEFAULT CHARACTER SET utf8;
grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry';

create database nav DEFAULT CHARACTER SET utf8;
grant all on nav.* TO 'nav'@'%' IDENTIFIED BY 'nav';

create database navms DEFAULT CHARACTER SET utf8;
grant all on navms.* TO 'navms'@'%' IDENTIFIED BY 'navms';

``` 