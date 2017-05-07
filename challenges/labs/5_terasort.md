# Terasort with neymar credentials

```

	[neymar@cloudera-1 ~]$ hadoop fs -ls /user/neymar
	Found 2 items
	drwx------   - neymar supergroup          0 2017-05-06 21:56 /user/neymar/.staging
	drwxr-xr-x   - neymar supergroup          0 2017-05-06 21:56 /user/neymar/tgen640
	[neymar@cloudera-1 ~]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/neymar/tgen640 /user/neymar/tsort640m

```

# Terasort output

```

	[neymar@cloudera-1 ~]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/neymar/tgen640 /user/neymar/tsort640m
	17/05/07 01:10:58 INFO terasort.TeraSort: starting
	17/05/07 01:11:00 INFO hdfs.DFSClient: Created token for neymar: HDFS_DELEGATION_TOKEN owner=neymar@AMOMMENDES.ES, renewer=yarn, realUser=, issueDate=1494119460328, maxDate=1494724260328, sequenceNumber=1, masterKeyId=8 on ha-hdfs:nameservice1
	17/05/07 01:11:00 INFO security.TokenCache: Got dt for hdfs://nameservice1; Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:nameservice1, Ident: (token for neymar: HDFS_DELEGATION_TOKEN owner=neymar@AMOMMENDES.ES, renewer=yarn, realUser=, issueDate=1494119460328, maxDate=1494724260328, sequenceNumber=1, masterKeyId=8)
	17/05/07 01:11:00 INFO input.FileInputFormat: Total input paths to process : 8
	Spent 421ms computing base-splits.
	Spent 6ms computing TeraScheduler splits.
	Computing input splits took 428ms
	Sampling 10 splits of 392
	Making 3 from 100000 sampled records
	Computing parititions took 2177ms
	Spent 2608ms computing partitions.
	17/05/07 01:11:02 INFO client.RMProxy: Connecting to ResourceManager at cloudera-1.c.cloudera-165315.internal/10.128.0.2:8032
	17/05/07 01:11:03 INFO mapreduce.JobSubmitter: number of splits:392
	17/05/07 01:11:03 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494116318260_0001
	17/05/07 01:11:03 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:nameservice1, Ident: (token for neymar: HDFS_DELEGATION_TOKEN owner=neymar@AMOMMENDES.ES, renewer=yarn, realUser=, issueDate=1494119460328, maxDate=1494724260328, sequenceNumber=1, masterKeyId=8)
	17/05/07 01:11:04 INFO impl.YarnClientImpl: Submitted application application_1494116318260_0001
	17/05/07 01:11:04 INFO mapreduce.Job: The url to track the job: http://cloudera-1.c.cloudera-165315.internal:8088/proxy/application_1494116318260_0001/
	17/05/07 01:11:04 INFO mapreduce.Job: Running job: job_1494116318260_0001
	17/05/07 01:11:19 INFO mapreduce.Job: Job job_1494116318260_0001 running in uber mode : false
	17/05/07 01:11:19 INFO mapreduce.Job:  map 0% reduce 0%
	17/05/07 01:11:38 INFO mapreduce.Job:  map 1% reduce 0%
	17/05/07 01:11:50 INFO mapreduce.Job:  map 2% reduce 0%
	17/05/07 01:12:03 INFO mapreduce.Job:  map 3% reduce 0%
	17/05/07 01:12:14 INFO mapreduce.Job:  map 4% reduce 0%
	17/05/07 01:12:28 INFO mapreduce.Job:  map 5% reduce 0%
	17/05/07 01:12:42 INFO mapreduce.Job:  map 6% reduce 0%
	17/05/07 01:12:56 INFO mapreduce.Job:  map 7% reduce 0%
	17/05/07 01:13:09 INFO mapreduce.Job:  map 8% reduce 0%
	17/05/07 01:13:20 INFO mapreduce.Job:  map 9% reduce 0%
	17/05/07 01:13:32 INFO mapreduce.Job:  map 10% reduce 0%
	17/05/07 01:13:43 INFO mapreduce.Job:  map 11% reduce 0%
	17/05/07 01:13:59 INFO mapreduce.Job:  map 12% reduce 0%
	17/05/07 01:14:07 INFO mapreduce.Job:  map 13% reduce 0%
	17/05/07 01:14:22 INFO mapreduce.Job:  map 14% reduce 0%
	17/05/07 01:14:37 INFO mapreduce.Job:  map 15% reduce 0%
	17/05/07 01:14:53 INFO mapreduce.Job:  map 16% reduce 0%
	17/05/07 01:15:04 INFO mapreduce.Job:  map 17% reduce 0%
	17/05/07 01:15:17 INFO mapreduce.Job:  map 18% reduce 0%
	17/05/07 01:15:28 INFO mapreduce.Job:  map 19% reduce 0%
	17/05/07 01:15:41 INFO mapreduce.Job:  map 20% reduce 0%
	17/05/07 01:15:57 INFO mapreduce.Job:  map 21% reduce 0%
	17/05/07 01:16:13 INFO mapreduce.Job:  map 22% reduce 0%
	17/05/07 01:16:25 INFO mapreduce.Job:  map 23% reduce 0%
	17/05/07 01:16:36 INFO mapreduce.Job:  map 24% reduce 0%
	17/05/07 01:16:47 INFO mapreduce.Job:  map 25% reduce 0%
	17/05/07 01:16:59 INFO mapreduce.Job:  map 26% reduce 0%
	17/05/07 01:17:09 INFO mapreduce.Job:  map 27% reduce 0%
	17/05/07 01:17:24 INFO mapreduce.Job:  map 28% reduce 0%
	17/05/07 01:17:39 INFO mapreduce.Job:  map 29% reduce 0%
	17/05/07 01:17:51 INFO mapreduce.Job:  map 30% reduce 0%
	17/05/07 01:18:02 INFO mapreduce.Job:  map 31% reduce 0%
	17/05/07 01:18:13 INFO mapreduce.Job:  map 32% reduce 0%
	17/05/07 01:18:28 INFO mapreduce.Job:  map 33% reduce 0%
	17/05/07 01:18:45 INFO mapreduce.Job:  map 34% reduce 0%
	17/05/07 01:18:57 INFO mapreduce.Job:  map 35% reduce 0%
	17/05/07 01:19:09 INFO mapreduce.Job:  map 36% reduce 0%
	17/05/07 01:19:20 INFO mapreduce.Job:  map 37% reduce 0%
	17/05/07 01:19:31 INFO mapreduce.Job:  map 38% reduce 0%
	17/05/07 01:19:42 INFO mapreduce.Job:  map 39% reduce 0%
	17/05/07 01:19:57 INFO mapreduce.Job:  map 40% reduce 0%
	17/05/07 01:20:12 INFO mapreduce.Job:  map 41% reduce 0%
	17/05/07 01:20:24 INFO mapreduce.Job:  map 42% reduce 0%
	17/05/07 01:20:36 INFO mapreduce.Job:  map 43% reduce 0%
	17/05/07 01:20:47 INFO mapreduce.Job:  map 44% reduce 0%
	17/05/07 01:20:59 INFO mapreduce.Job:  map 45% reduce 0%
	17/05/07 01:21:16 INFO mapreduce.Job:  map 46% reduce 0%
	17/05/07 01:21:29 INFO mapreduce.Job:  map 47% reduce 0%
	17/05/07 01:21:40 INFO mapreduce.Job:  map 48% reduce 0%
	17/05/07 01:21:53 INFO mapreduce.Job:  map 49% reduce 0%
	17/05/07 01:22:04 INFO mapreduce.Job:  map 50% reduce 0%
	17/05/07 01:22:15 INFO mapreduce.Job:  map 51% reduce 0%
	17/05/07 01:22:28 INFO mapreduce.Job:  map 52% reduce 0%
	17/05/07 01:22:43 INFO mapreduce.Job:  map 53% reduce 0%
	17/05/07 01:22:56 INFO mapreduce.Job:  map 54% reduce 0%
	17/05/07 01:23:08 INFO mapreduce.Job:  map 55% reduce 0%
	17/05/07 01:23:19 INFO mapreduce.Job:  map 56% reduce 0%
	17/05/07 01:23:31 INFO mapreduce.Job:  map 57% reduce 0%
	17/05/07 01:23:46 INFO mapreduce.Job:  map 58% reduce 0%
	17/05/07 01:24:02 INFO mapreduce.Job:  map 59% reduce 0%
	17/05/07 01:24:13 INFO mapreduce.Job:  map 60% reduce 0%
	17/05/07 01:24:26 INFO mapreduce.Job:  map 61% reduce 0%
	17/05/07 01:24:36 INFO mapreduce.Job:  map 62% reduce 0%
	17/05/07 01:24:47 INFO mapreduce.Job:  map 63% reduce 0%
	17/05/07 01:24:59 INFO mapreduce.Job:  map 64% reduce 0%
	17/05/07 01:25:15 INFO mapreduce.Job:  map 65% reduce 0%
	17/05/07 01:25:30 INFO mapreduce.Job:  map 66% reduce 0%
	17/05/07 01:25:40 INFO mapreduce.Job:  map 67% reduce 0%
	17/05/07 01:25:52 INFO mapreduce.Job:  map 68% reduce 0%
	17/05/07 01:26:03 INFO mapreduce.Job:  map 69% reduce 0%
	17/05/07 01:26:17 INFO mapreduce.Job:  map 70% reduce 0%
	17/05/07 01:26:33 INFO mapreduce.Job:  map 71% reduce 0%
	17/05/07 01:26:46 INFO mapreduce.Job:  map 72% reduce 0%
	17/05/07 01:26:57 INFO mapreduce.Job:  map 73% reduce 0%
	17/05/07 01:27:10 INFO mapreduce.Job:  map 74% reduce 0%
	17/05/07 01:27:21 INFO mapreduce.Job:  map 75% reduce 0%
	17/05/07 01:27:31 INFO mapreduce.Job:  map 76% reduce 0%
	17/05/07 01:27:45 INFO mapreduce.Job:  map 77% reduce 0%
	17/05/07 01:28:01 INFO mapreduce.Job:  map 78% reduce 0%
	17/05/07 01:28:14 INFO mapreduce.Job:  map 79% reduce 0%
	17/05/07 01:28:25 INFO mapreduce.Job:  map 80% reduce 0%
	17/05/07 01:28:41 INFO mapreduce.Job:  map 81% reduce 0%
	17/05/07 01:29:22 INFO mapreduce.Job:  map 82% reduce 0%
	17/05/07 01:29:44 INFO mapreduce.Job:  map 83% reduce 0%
	17/05/07 01:30:06 INFO mapreduce.Job:  map 84% reduce 0%
	17/05/07 01:30:16 INFO mapreduce.Job:  map 84% reduce 4%
	17/05/07 01:30:22 INFO mapreduce.Job:  map 84% reduce 6%
	17/05/07 01:30:25 INFO mapreduce.Job:  map 84% reduce 12%
	17/05/07 01:30:29 INFO mapreduce.Job:  map 84% reduce 14%
	17/05/07 01:30:31 INFO mapreduce.Job:  map 84% reduce 16%
	17/05/07 01:30:35 INFO mapreduce.Job:  map 84% reduce 17%
	17/05/07 01:30:37 INFO mapreduce.Job:  map 84% reduce 19%
	17/05/07 01:30:40 INFO mapreduce.Job:  map 85% reduce 19%
	17/05/07 01:31:08 INFO mapreduce.Job:  map 86% reduce 19%
	17/05/07 01:31:35 INFO mapreduce.Job:  map 87% reduce 19%
	C17/05/07 01:31:55 INFO mapreduce.Job:  map 88% reduce 19%
	17/05/07 01:32:07 INFO mapreduce.Job:  map 88% reduce 20%
	17/05/07 01:32:24 INFO mapreduce.Job:  map 89% reduce 20%
	17/05/07 01:32:51 INFO mapreduce.Job:  map 90% reduce 20%
	17/05/07 01:33:25 INFO mapreduce.Job:  map 91% reduce 20%
	17/05/07 01:33:54 INFO mapreduce.Job:  map 92% reduce 20%
	17/05/07 01:34:20 INFO mapreduce.Job:  map 92% reduce 21%
	17/05/07 01:34:23 INFO mapreduce.Job:  map 93% reduce 21%
	17/05/07 01:34:52 INFO mapreduce.Job:  map 94% reduce 21%
	17/05/07 01:35:19 INFO mapreduce.Job:  map 95% reduce 21%
	17/05/07 01:35:53 INFO mapreduce.Job:  map 96% reduce 21%
	17/05/07 01:36:24 INFO mapreduce.Job:  map 97% reduce 21%
	17/05/07 01:36:36 INFO mapreduce.Job:  map 97% reduce 22%
	17/05/07 01:36:53 INFO mapreduce.Job:  map 98% reduce 22%
	17/05/07 01:37:22 INFO mapreduce.Job:  map 99% reduce 22%
	17/05/07 01:37:50 INFO mapreduce.Job:  map 100% reduce 22%
	17/05/07 01:38:00 INFO mapreduce.Job:  map 100% reduce 33%
	17/05/07 01:38:01 INFO mapreduce.Job:  map 100% reduce 45%
	17/05/07 01:38:06 INFO mapreduce.Job:  map 100% reduce 46%
	17/05/07 01:38:07 INFO mapreduce.Job:  map 100% reduce 48%
	17/05/07 01:38:13 INFO mapreduce.Job:  map 100% reduce 49%
	17/05/07 01:38:14 INFO mapreduce.Job:  map 100% reduce 51%
	17/05/07 01:38:19 INFO mapreduce.Job:  map 100% reduce 56%
	17/05/07 01:38:20 INFO mapreduce.Job:  map 100% reduce 58%
	17/05/07 01:38:25 INFO mapreduce.Job:  map 100% reduce 62%
	17/05/07 01:38:26 INFO mapreduce.Job:  map 100% reduce 64%
	17/05/07 01:38:31 INFO mapreduce.Job:  map 100% reduce 67%
	17/05/07 01:38:32 INFO mapreduce.Job:  map 100% reduce 69%
	17/05/07 01:38:34 INFO mapreduce.Job:  map 100% reduce 70%
	17/05/07 01:38:37 INFO mapreduce.Job:  map 100% reduce 73%
	17/05/07 01:38:43 INFO mapreduce.Job:  map 100% reduce 76%
	17/05/07 01:38:49 INFO mapreduce.Job:  map 100% reduce 89%
	17/05/07 01:38:55 INFO mapreduce.Job:  map 100% reduce 91%
	17/05/07 01:39:01 INFO mapreduce.Job:  map 100% reduce 93%
	17/05/07 01:39:07 INFO mapreduce.Job:  map 100% reduce 96%
	17/05/07 01:39:13 INFO mapreduce.Job:  map 100% reduce 98%
	17/05/07 01:39:18 INFO mapreduce.Job:  map 100% reduce 100%
	17/05/07 01:39:19 INFO mapreduce.Job: Job job_1494116318260_0001 completed successfully
	17/05/07 01:39:19 INFO mapreduce.Job: Counters: 55
	        File System Counters
	                FILE: Number of bytes read=2938450134
	                FILE: Number of bytes written=5854771010
	                FILE: Number of read operations=0
	                FILE: Number of large read operations=0
	                FILE: Number of write operations=0
	                HDFS: Number of bytes read=6553645864
	                HDFS: Number of bytes written=6553600000
	                HDFS: Number of read operations=1185
	                HDFS: Number of large read operations=0
	                HDFS: Number of write operations=6
	        Job Counters 
	                Killed reduce tasks=2
	                Launched map tasks=392
	                Launched reduce tasks=5
	                Data-local map tasks=390
	                Rack-local map tasks=2
	                Total time spent by all maps in occupied slots (ms)=3214349
	                Total time spent by all reduces in occupied slots (ms)=1131080
	                Total time spent by all map tasks (ms)=3214349
	                Total time spent by all reduce tasks (ms)=1131080
	                Total vcore-milliseconds taken by all map tasks=3214349
	                Total vcore-milliseconds taken by all reduce tasks=1131080
	                Total megabyte-milliseconds taken by all map tasks=3291493376
	                Total megabyte-milliseconds taken by all reduce tasks=1158225920
	        Map-Reduce Framework
	                Map input records=65536000
	                Map output records=65536000
	                Map output bytes=6684672000
	                Map output materialized bytes=2864275245
	                Input split bytes=45864
	                Combine input records=0
	                Combine output records=0
	                Reduce input groups=65536000
	                Reduce shuffle bytes=2864275245
	                Reduce input records=65536000
	                Reduce output records=65536000
	                Spilled Records=131072000
	                Shuffled Maps =1176
	                Failed Shuffles=0
	                Merged Map outputs=1176
	                GC time elapsed (ms)=34953
	                CPU time spent (ms)=1410170
	                Physical memory (bytes) snapshot=187394187264
	                Virtual memory (bytes) snapshot=616010510336
	                Total committed heap usage (bytes)=207511617536
	                Peak Map Physical memory (bytes)=499802112
	                Peak Map Virtual memory (bytes)=1572478976
	                Peak Reduce Physical memory (bytes)=980480000
	                Peak Reduce Virtual memory (bytes)=1581907968
	        Shuffle Errors
	                BAD_ID=0
	                CONNECTION=0
	                IO_ERROR=0
	                WRONG_LENGTH=0
	                WRONG_MAP=0
	                WRONG_REDUCE=0
	        File Input Format Counters 
	                Bytes Read=6553600000
	        File Output Format Counters 
	                Bytes Written=6553600000
	17/05/07 01:39:19 INFO terasort.TeraSort: done

```