# Teragen command with Neymar

```

	[neymar@cloudera-2 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=8 -Ddfs.block.size=16777216 65536000 /user/neymar/tgen640
	17/05/06 21:54:58 INFO client.RMProxy: Connecting to ResourceManager at cloudera-1.c.cloudera-165315.internal/10.128.0.2:8032
	^[[H17/05/06 21:54:59 INFO terasort.TeraGen: Generating 65536000 using 8
	17/05/06 21:54:59 INFO mapreduce.JobSubmitter: number of splits:8
	17/05/06 21:54:59 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
	17/05/06 21:54:59 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
	17/05/06 21:55:00 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494105705269_0001
	17/05/06 21:55:00 INFO impl.YarnClientImpl: Submitted application application_1494105705269_0001
	17/05/06 21:55:00 INFO mapreduce.Job: The url to track the job: http://cloudera-1.c.cloudera-165315.internal:8088/proxy/application_1494105705269_0001/
	17/05/06 21:55:00 INFO mapreduce.Job: Running job: job_1494105705269_0001
	17/05/06 21:55:10 INFO mapreduce.Job: Job job_1494105705269_0001 running in uber mode : false
	17/05/06 21:55:10 INFO mapreduce.Job:  map 0% reduce 0%
	17/05/06 21:55:29 INFO mapreduce.Job:  map 9% reduce 0%
	17/05/06 21:55:34 INFO mapreduce.Job:  map 21% reduce 0%
	17/05/06 21:55:40 INFO mapreduce.Job:  map 29% reduce 0%
	17/05/06 21:55:46 INFO mapreduce.Job:  map 35% reduce 0%
	17/05/06 21:55:47 INFO mapreduce.Job:  map 36% reduce 0%
	17/05/06 21:55:48 INFO mapreduce.Job:  map 38% reduce 0%
	17/05/06 21:55:53 INFO mapreduce.Job:  map 46% reduce 0%
	17/05/06 21:55:56 INFO mapreduce.Job:  map 50% reduce 0%
	17/05/06 21:56:10 INFO mapreduce.Job:  map 60% reduce 0%
	17/05/06 21:56:15 INFO mapreduce.Job:  map 67% reduce 0%
	17/05/06 21:56:16 INFO mapreduce.Job:  map 73% reduce 0%
	17/05/06 21:56:21 INFO mapreduce.Job:  map 78% reduce 0%
	17/05/06 21:56:22 INFO mapreduce.Job:  map 84% reduce 0%
	17/05/06 21:56:24 INFO mapreduce.Job:  map 88% reduce 0%
	17/05/06 21:56:39 INFO mapreduce.Job:  map 98% reduce 0%
	17/05/06 21:56:41 INFO mapreduce.Job:  map 100% reduce 0%
	17/05/06 21:56:42 INFO mapreduce.Job: Job job_1494105705269_0001 completed successfully
	17/05/06 21:56:43 INFO mapreduce.Job: Counters: 33
	        File System Counters
	                FILE: Number of bytes read=0
	                FILE: Number of bytes written=1020504
	                FILE: Number of read operations=0
	                FILE: Number of large read operations=0
	                FILE: Number of write operations=0
	                HDFS: Number of bytes read=682
	                HDFS: Number of bytes written=6553600000
	                HDFS: Number of read operations=32
	                HDFS: Number of large read operations=0
	                HDFS: Number of write operations=16
	        Job Counters 
	                Launched map tasks=8
	                Other local map tasks=8
	                Total time spent by all maps in occupied slots (ms)=228166
	                Total time spent by all reduces in occupied slots (ms)=0
	                Total time spent by all map tasks (ms)=228166
	                Total vcore-milliseconds taken by all map tasks=228166
	                Total megabyte-milliseconds taken by all map tasks=233641984
	        Map-Reduce Framework
	                Map input records=65536000
	                Map output records=65536000
	                Input split bytes=682
	                Spilled Records=0
	                Failed Shuffles=0
	                Merged Map outputs=0
	                GC time elapsed (ms)=1899
	                CPU time spent (ms)=143220
	                Physical memory (bytes) snapshot=2818867200
	                Virtual memory (bytes) snapshot=12466860032
	                Total committed heap usage (bytes)=2773483520
	                Peak Map Physical memory (bytes)=376582144
	                Peak Map Virtual memory (bytes)=1562447872
	        org.apache.hadoop.examples.terasort.TeraGen$Counters
	                CHECKSUM=140750829423462787
	        File Input Format Counters 
	                Bytes Read=0
	        File Output Format Counters 
	                Bytes Written=6553600000

```

# Time

```

	real    1m47.002s
	user    0m5.441s
	sys     0m0.329s

```

# Output

``` 

	[neymar@cloudera-2 ~]$ hdfs dfs -ls /user/neymar/tgen640
	Found 9 items
	-rw-r--r--   3 neymar supergroup          0 2017-05-06 21:56 /user/neymar/tgen640/_SUCCESS
	-rw-r--r--   3 neymar supergroup  819200000 2017-05-06 21:55 /user/neymar/tgen640/part-m-00000
	-rw-r--r--   3 neymar supergroup  819200000 2017-05-06 21:55 /user/neymar/tgen640/part-m-00001
	-rw-r--r--   3 neymar supergroup  819200000 2017-05-06 21:55 /user/neymar/tgen640/part-m-00002
	-rw-r--r--   3 neymar supergroup  819200000 2017-05-06 21:55 /user/neymar/tgen640/part-m-00003
	-rw-r--r--   3 neymar supergroup  819200000 2017-05-06 21:56 /user/neymar/tgen640/part-m-00004
	-rw-r--r--   3 neymar supergroup  819200000 2017-05-06 21:56 /user/neymar/tgen640/part-m-00005
	-rw-r--r--   3 neymar supergroup  819200000 2017-05-06 21:56 /user/neymar/tgen640/part-m-00006
	-rw-r--r--   3 neymar supergroup  819200000 2017-05-06 21:56 /user/neymar/tgen640/part-m-00007
```



```

	[neymar@cloudera-2 ~]$ hdfs  fsck /user/neymar/tgen640 -blocks
	Connecting to namenode via http://cloudera-1.c.cloudera-165315.internal:50070
	FSCK started by neymar (auth:SIMPLE) from /10.128.0.3 for path /user/neymar/tgen640 at Sat May 06 21:59:57 UTC 2017
	.........Status: HEALTHY
	 Total size:    6553600000 B
	 Total dirs:    1
	 Total files:   9
	 Total symlinks:                0
	 Total blocks (validated):      392 (avg. block size 16718367 B)
	 Minimally replicated blocks:   392 (100.0 %)
	 Over-replicated blocks:        0 (0.0 %)
	 Under-replicated blocks:       0 (0.0 %)
	 Mis-replicated blocks:         0 (0.0 %)
	 Default replication factor:    3
	 Average block replication:     3.0
	 Corrupt blocks:                0
	 Missing replicas:              0 (0.0 %)
	 Number of data-nodes:          3
	 Number of racks:               1
	FSCK ended at Sat May 06 21:59:57 UTC 2017 in 17 milliseconds


	The filesystem under path '/user/neymar/tgen640' is HEALTHY
```