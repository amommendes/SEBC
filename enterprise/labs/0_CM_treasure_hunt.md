* What is ubertask optimization?

ubertask runs jobs "little" jobs sequentially in a unique JVM. "Little" is defined by configurations, as mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces as mapreduce.job.ubertask.maxbytes.

* Where in CM is the Kerberos Security Realm value displayed?

Administration >> Configurations

* Which CDH service(s) host a property for enabling Kerberos authentication?

- HDFS
- Yarn
- Zookeper
- Hue
- Hive

* How do you upgrade the CM agents?

Hosts > Upgrading Wizard

* Give the tsquery statement used to chart Hue's CPU utilization?

```
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME
```

* Name all the roles that make up the Hive service

- Hive Metastore Server
- HiveServer2

* What steps must be completed before integrating Cloudera Manager with Kerberos?

Step 1: Install Cloudera Manager and CDH
Step 2: If You are Using AES-256 Encryption, Install the JCE Policy File
Step 3: Get or Create a Kerberos Principal for the Cloudera Manager Server