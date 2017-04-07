# Command kinit 
 
```

cd /var/run/cloudera-scm-agent/process/230-hdfs-NAMENODE/
kinit hdfs/ip-10-0-1-19.sa-east-1.compute.internal@SA-EAST-1.COMPUTE.INTERNAL -kt hdfs.keytab 

[root@ip-10-0-1-19 230-hdfs-NAMENODE]# hadoop fs -ls /
Found 5 items
drwxr-xr-x   - hdfs supergroup          0 2017-04-06 18:55 /kerb
drwxr-xr-x   - hdfs supergroup          0 2017-04-05 15:00 /precious
drwxr-xr-x   - hdfs supergroup          0 2017-04-06 00:29 /results
drwxrwxrwt   - hdfs supergroup          0 2017-04-05 12:02 /tmp
drwxr-xr-x   - hdfs supergroup          0 2017-04-05 13:43 /user

``` 

# klist

```
[root@ip-10-0-1-19 pki]# klist

Ticket cache: FILE:/tmp/krb5cc_0
Default principal: hdfs/ip-10-0-1-19.sa-east-1.compute.internal@SA-EAST-1.COMPUTE.INTERNAL

Valid starting       Expires              Service principal
04/06/2017 18:55:05  04/07/2017 18:55:05  krbtgt/SA-EAST-1.COMPUTE.INTERNAL@SA-EAST-1.COMPUTE.INTERNAL   renew until 04/13/2017 18:55:05
```