# Hostname MariaDB Server 

```
	
	[root@cloudera-1 ~]# hostname -f
	cloudera-1.c.cloudera-165315.internal
```

# Hostname MariaDB Slave

```
	
	[root@cloudera-2 ~]# hostname -f
	cloudera-2.c.cloudera-165315.internal
```


# DB Version

```
	
	[root@cloudera-1 ~]# mysql --version
	mysql  Ver 15.1 Distrib 10.1.23-MariaDB, for Linux (x86_64) using readline 5.1
```

#/etc/my.cnf

```
	
	[mysqld]
	# Disabling symbolic-links is recommended to prevent assorted security risks;
	# to do so, uncomment this line:
	# symbolic-links = 0
	# Nao esquecer do server id
	server_id=1
	transaction-isolation = READ-COMMITTED
	key_buffer = 16M
	key_buffer_size = 32M
	max_allowed_packet = 64M
	#max_allowed_packet = 32M
	thread_stack = 256K
	thread_cache_size = 64
	query_cache_limit = 8M
	query_cache_size = 64M
	query_cache_type = 1

	max_connections = 550
	#expire_logs_days = 10
	#max_binlog_size = 100M

	#log_bin should be on a disk with enough free space. Replace '/var/lib/mysql/mysql_binary_log' with an appropriate path for your system
	#and chown the specified folder to the mysql user.
	log_bin=/var/lib/mysql/mysql_binary_log

	binlog_format = mixed

	read_buffer_size = 2M
	read_rnd_buffer_size = 16M
	sort_buffer_size = 8M
	join_buffer_size = 8M

	# InnoDB settings
	innodb_file_per_table = 1
	innodb_flush_log_at_trx_commit  = 2
	innodb_log_buffer_size = 64M
	innodb_buffer_pool_size = 4G
	innodb_thread_concurrency = 8
	innodb_flush_method = O_DIRECT
	innodb_log_file_size = 512M

	[mysqld_safe]
	log-error=/var/log/mariadb/mariadb.log
	pid-file=/var/run/mariadb/mariadb.pid


```
# Replication

```

	[root@cloudera-2 ~]# mysql -uroot -p
	Enter password: 
	Welcome to the MariaDB monitor.  Commands end with ; or \g.
	Your MariaDB connection id is 15
	Server version: 10.1.23-MariaDB MariaDB Server

	Copyright (c) 2000, 2017, Oracle, MariaDB Corporation Ab and others.

	Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

	MariaDB [(none)]> show slave status \G
	*************************** 1. row ***************************
	               Slave_IO_State: Waiting for master to send event
	                  Master_Host: 10.128.0.2
	                  Master_User: replica
	                  Master_Port: 3306
	                Connect_Retry: 10
	              Master_Log_File: mysql_binary_log.000001
	          Read_Master_Log_Pos: 1769
	               Relay_Log_File: cloudera-2-relay-bin.000002
	                Relay_Log_Pos: 2064
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
	          Exec_Master_Log_Pos: 1769
	              Relay_Log_Space: 2367
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
	                  Gtid_IO_Pos: 0-1-9
	      Replicate_Do_Domain_Ids: 
	  Replicate_Ignore_Domain_Ids: 
	                Parallel_Mode: conservative
	1 row in set (0.00 sec)

```
# Databases created

```

	[root@cloudera-1 ~]# mysql -uroot -p
	Enter password: 
	MariaDB [(none)]> show databases;
	+--------------------+
	| Database           |
	+--------------------+
	| amon               |
	| hue                |
	| information_schema |
	| metastore          |
	| mysql              |
	| nav                |
	| navms              |
	| oozie              |
	| performance_schema |
	| rman               |
	| sentry             |
	+--------------------+
	11 rows in set (0.00 sec)

``` 