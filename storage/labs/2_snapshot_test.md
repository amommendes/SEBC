# Create directory

```
 sudo -u hdfs hadoop fs -mkdir /precious

[amommendes@ip-10-0-1-19 hadoop-mapreduce]$ hadoop fs -ls /
Found 3 items
drwxr-xr-x   - hdfs supergroup          0 2017-04-05 14:04 /precious
drwxrwxrwt   - hdfs supergroup          0 2017-04-05 12:02 /tmp
drwxr-xr-x   - hdfs supergroup          0 2017-04-05 13:43 /user

```

# Zip File

```
[amommendes@ip-10-0-1-19 /]$ cd /home/amommendes/

[amommendes@ip-10-0-1-19 ~]$ wget https://github.com/amommendes/SEBC/archive/master.zip

[amommendes@ip-10-0-1-19 ~]$ mv master.zip /tmp/sebc.zip

[amommendes@ip-10-0-1-19 tmp]$ sudo -u hdfs hadoop fs -put ./sebc.zip  /precious

[amommendes@ip-10-0-1-19 tmp]$ hadoop fs -ls /precious/
Found 1 items
-rw-r--r--   3 hdfs supergroup     681492 2017-04-05 14:19 /precious/sebc.zip

[amommendes@ip-10-0-1-19 tmp]$ sudo -u hdfs hdfs dfsadmin -allowSnapshot /precious
Allowing snaphot on /precious succeeded

[amommendes@ip-10-0-1-19 tmp]$ sudo -u hdfs hdfs dfs -createSnapshot /precious sebc-hdfs-test
Created snapshot /precious/.snapshot/sebc-hdfs-test

[amommendes@ip-10-0-1-19 tmp]$ sudo -u hdfs hadoop fs -rm -r /precious
rm: Failed to move to trash: hdfs://ip-10-0-1-19.sa-east-1.compute.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots

[amommendes@ip-10-0-1-19 tmp]$ sudo -u hdfs hadoop fs -rm -r /precious/sebc.zip
17/04/05 14:30:47 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-10-0-1-19.sa-east-1.compute.internal:8020/precious/sebc.zip' to trash at: hdfs://ip-10-0-1-19.sa-east-1.compute.internal:8020/user/hdfs/.Trash/Current/precious/sebc.zip


[amommendes@ip-10-0-1-19 tmp]$ sudo -u hdfs hadoop fs -ls /precious/.snapshot/sebc-hdfs-test
Found 1 items
-rw-r--r--   3 hdfs supergroup     681492 2017-04-05 14:19 /precious/.snapshot/sebc-hdfs-test/sebc.zip


[amommendes@ip-10-0-1-19 tmp]$ sudo -u hdfs hadoop fs -ls /precious/.snapshot/sebc-hdfs-test
Found 1 items
-rw-r--r--   3 hdfs supergroup     681492 2017-04-05 14:19 /precious/.snapshot/sebc-hdfs-test/sebc.zip

[amommendes@ip-10-0-1-19 tmp]$ sudo -u hdfs hadoop fs -cp /precious/.snapshot/sebc-hdfs-test/sebc.zip /precious

[amommendes@ip-10-0-1-19 tmp]$ sudo -u hdfs hadoop fs -ls /precious/
Found 1 items
-rw-r--r--   3 hdfs supergroup     681492 2017-04-05 14:36 /precious/sebc.zip


```