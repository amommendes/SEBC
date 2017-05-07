# Pi command with ronaldo credentials

```
	
	[ronaldo@cloudera-1 ~]$ klist
	Ticket cache: FILE:/tmp/krb5cc_2016
	Default principal: ronaldo@AMOMMENDES.ES

	Valid starting     Expires            Service principal
	05/07/17 01:41:21  05/08/17 01:41:21  krbtgt/AMOMMENDES.ES@AMOMMENDES.ES
	        renew until 05/14/17 01:41:21
	[ronaldo@cloudera-1 ~]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar pi 8 2048
	Number of Maps  = 8
	Samples per Map = 2048
	Wrote input for Map #0
	Wrote input for Map #1
	Wrote input for Map #2
	Wrote input for Map #3
	Wrote input for Map #4
	Wrote input for Map #5
	Wrote input for Map #6
	Wrote input for Map #7
	Starting Job
	17/05/07 01:42:07 INFO client.RMProxy: Connecting to ResourceManager at cloudera-1.c.cloudera-165315.internal/10.128.0.2:8032
	17/05/07 01:42:07 INFO hdfs.DFSClient: Created token for ronaldo: HDFS_DELEGATION_TOKEN owner=ronaldo@AMOMMENDES.ES, renewer=yarn, realUser=, issueDate=1494121327428, maxDate=1494726127428, sequenceNumber=3, masterKeyId=8 on ha-hdfs:nameservice1
	17/05/07 01:42:07 INFO security.TokenCache: Got dt for hdfs://nameservice1; Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:nameservice1, Ident: (token for ronaldo: HDFS_DELEGATION_TOKEN owner=ronaldo@AMOMMENDES.ES, renewer=yarn, realUser=, issueDate=1494121327428, maxDate=1494726127428, sequenceNumber=3, masterKeyId=8)
	17/05/07 01:42:07 INFO input.FileInputFormat: Total input paths to process : 8
	17/05/07 01:42:08 INFO mapreduce.JobSubmitter: number of splits:8
	17/05/07 01:42:08 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494116318260_0003
	17/05/07 01:42:08 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:nameservice1, Ident: (token for ronaldo: HDFS_DELEGATION_TOKEN owner=ronaldo@AMOMMENDES.ES, renewer=yarn, realUser=, issueDate=1494121327428, maxDate=1494726127428, sequenceNumber=3, masterKeyId=8)
	17/05/07 01:42:08 INFO impl.YarnClientImpl: Submitted application application_1494116318260_0003
	17/05/07 01:42:08 INFO mapreduce.Job: The url to track the job: http://cloudera-1.c.cloudera-165315.internal:8088/proxy/application_1494116318260_0003/
	17/05/07 01:42:08 INFO mapreduce.Job: Running job: job_1494116318260_0003
	17/05/07 01:42:18 INFO mapreduce.Job: Job job_1494116318260_0003 running in uber mode : false
	17/05/07 01:42:18 INFO mapreduce.Job:  map 0% reduce 0%
	17/05/07 01:42:29 INFO mapreduce.Job:  map 38% reduce 0%
	17/05/07 01:42:34 INFO mapreduce.Job:  map 50% reduce 0%
	17/05/07 01:42:35 INFO mapreduce.Job:  map 63% reduce 0%
	17/05/07 01:42:36 INFO mapreduce.Job:  map 75% reduce 0%
	17/05/07 01:42:39 INFO mapreduce.Job:  map 88% reduce 0%
	17/05/07 01:42:41 INFO mapreduce.Job:  map 100% reduce 0%
	17/05/07 01:42:47 INFO mapreduce.Job:  map 100% reduce 100%
	17/05/07 01:42:47 INFO mapreduce.Job: Job job_1494116318260_0003 completed successfully
	17/05/07 01:42:47 INFO mapreduce.Job: Counters: 53
	        File System Counters
	                FILE: Number of bytes read=90
	                FILE: Number of bytes written=1179306
	                FILE: Number of read operations=0
	                FILE: Number of large read operations=0
	                FILE: Number of write operations=0
	                HDFS: Number of bytes read=2112
	                HDFS: Number of bytes written=215
	                HDFS: Number of read operations=35
	                HDFS: Number of large read operations=0
	                HDFS: Number of write operations=3
	        Job Counters 
	                Launched map tasks=8
	                Launched reduce tasks=1
	                Data-local map tasks=8
	                Total time spent by all maps in occupied slots (ms)=50164
	                Total time spent by all reduces in occupied slots (ms)=4695
	                Total time spent by all map tasks (ms)=50164
	                Total time spent by all reduce tasks (ms)=4695
	                Total vcore-milliseconds taken by all map tasks=50164
	                Total vcore-milliseconds taken by all reduce tasks=4695
	                Total megabyte-milliseconds taken by all map tasks=51367936
	                Total megabyte-milliseconds taken by all reduce tasks=4807680
	        Map-Reduce Framework
	                Map input records=8
	                Map output records=16
	                Map output bytes=144
	                Map output materialized bytes=280
	                Input split bytes=1168
	                Combine input records=0
	                Combine output records=0
	                Reduce input groups=2
	                Reduce shuffle bytes=280
	                Reduce input records=16
	                Reduce output records=0
	                Spilled Records=32
	                Shuffled Maps =8
	                Failed Shuffles=0
	                Merged Map outputs=8
	                GC time elapsed (ms)=388
	                CPU time spent (ms)=6860
	                Physical memory (bytes) snapshot=4019724288
	                Virtual memory (bytes) snapshot=14054375424
	                Total committed heap usage (bytes)=4477943808
	                Peak Map Physical memory (bytes)=495702016
	                Peak Map Virtual memory (bytes)=1566511104
	                Peak Reduce Physical memory (bytes)=230453248
	                Peak Reduce Virtual memory (bytes)=1567612928
	        Shuffle Errors
	                BAD_ID=0
	                CONNECTION=0
	                IO_ERROR=0
	                WRONG_LENGTH=0
	                WRONG_MAP=0
	                WRONG_REDUCE=0
	        File Input Format Counters 
	                Bytes Read=944
	        File Output Format Counters 
	                Bytes Written=97
	Job Finished in 40.506 seconds
	Estimated value of Pi is 3.14111328125000000000

```