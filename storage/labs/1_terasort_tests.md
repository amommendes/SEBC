# Teragen

```

[amommendes@ip-10-0-1-19 hadoop-mapreduce]$ sudo -u hdfs time hadoop jar hadoop-mapreduce-examples.jar teragen -D dfs.block.size=32000000 10000000 /user/amommendes/data

17/04/05 13:43:58 INFO client.RMProxy: Connecting to ResourceManager at ip-10-0-1-19.sa-east-1.compute.internal/10.0.1.19:8032
17/04/05 13:43:58 INFO terasort.TeraGen: Generating 10000000 using 2
17/04/05 13:43:58 INFO mapreduce.JobSubmitter: number of splits:2
17/04/05 13:43:58 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/04/05 13:43:59 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1491373381238_0001
17/04/05 13:43:59 INFO impl.YarnClientImpl: Submitted application application_1491373381238_0001
17/04/05 13:43:59 INFO mapreduce.Job: The url to track the job: http://ip-10-0-1-19.sa-east-1.compute.internal:8088/proxy/application_1491373381238_0001/
17/04/05 13:43:59 INFO mapreduce.Job: Running job: job_1491373381238_0001
17/04/05 13:44:06 INFO mapreduce.Job: Job job_1491373381238_0001 running in uber mode : false
17/04/05 13:44:06 INFO mapreduce.Job:  map 0% reduce 0%
17/04/05 13:44:22 INFO mapreduce.Job:  map 100% reduce 0%
17/04/05 13:44:22 INFO mapreduce.Job: Job job_1491373381238_0001 completed successfully
17/04/05 13:44:22 INFO mapreduce.Job: Counters: 31

        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=249920
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=167
                HDFS: Number of bytes written=1000000000
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=4
        Job Counters 
                Launched map tasks=2
                Other local map tasks=2
                Total time spent by all maps in occupied slots (ms)=27076
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=27076
                Total vcore-seconds taken by all map tasks=27076
                Total megabyte-seconds taken by all map tasks=27725824
        Map-Reduce Framework
                Map input records=10000000
                Map output records=10000000
                Input split bytes=167
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=278
                CPU time spent (ms)=23310
                Physical memory (bytes) snapshot=749105152
                Virtual memory (bytes) snapshot=3183439872
                Total committed heap usage (bytes)=807403520
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=21472776955442690
        File Input Format Counters 
                Bytes Read=0
        File Output Format Counters 
                Bytes Written=1000000000

5.83user 0.29system 0:27.39elapsed 22%CPU (0avgtext+0avgdata 181788maxresident)k
0inputs+1816outputs (0major+59651minor)pagefaults 0swaps

```

# Terasort

```

[amommendes@ip-10-0-1-19 hadoop-mapreduce]$ sudo -u hdfs time  hadoop jar hadoop-mapreduce-examples.jar terasort /user/amommendes/data /user/amommendes/terasort-output

17/04/05 13:54:06 INFO terasort.TeraSort: starting
17/04/05 13:54:07 INFO input.FileInputFormat: Total input paths to process : 2
Spent 144ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 147ms
Sampling 10 splits of 32
Making 6 from 100000 sampled records
Computing parititions took 822ms
Spent 972ms computing partitions.
17/04/05 13:54:08 INFO client.RMProxy: Connecting to ResourceManager at ip-10-0-1-19.sa-east-1.compute.internal/10.0.1.19:8032
17/04/05 13:54:09 INFO mapreduce.JobSubmitter: number of splits:32
17/04/05 13:54:09 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1491373381238_0002
17/04/05 13:54:09 INFO impl.YarnClientImpl: Submitted application application_1491373381238_0002
17/04/05 13:54:09 INFO mapreduce.Job: The url to track the job: http://ip-10-0-1-19.sa-east-1.compute.internal:8088/proxy/application_1491373381238_0002/
17/04/05 13:54:09 INFO mapreduce.Job: Running job: job_1491373381238_0002
17/04/05 13:54:16 INFO mapreduce.Job: Job job_1491373381238_0002 running in uber mode : false
17/04/05 13:54:16 INFO mapreduce.Job:  map 0% reduce 0%
17/04/05 13:54:27 INFO mapreduce.Job:  map 6% reduce 0%
17/04/05 13:54:28 INFO mapreduce.Job:  map 9% reduce 0%
17/04/05 13:54:30 INFO mapreduce.Job:  map 22% reduce 0%
17/04/05 13:54:36 INFO mapreduce.Job:  map 25% reduce 0%
17/04/05 13:54:37 INFO mapreduce.Job:  map 28% reduce 0%
17/04/05 13:54:38 INFO mapreduce.Job:  map 31% reduce 0%
17/04/05 13:54:43 INFO mapreduce.Job:  map 38% reduce 0%
17/04/05 13:54:44 INFO mapreduce.Job:  map 44% reduce 0%
17/04/05 13:54:47 INFO mapreduce.Job:  map 47% reduce 0%
17/04/05 13:54:48 INFO mapreduce.Job:  map 53% reduce 0%
17/04/05 13:54:54 INFO mapreduce.Job:  map 56% reduce 0%
17/04/05 13:54:56 INFO mapreduce.Job:  map 66% reduce 0%
17/04/05 13:54:57 INFO mapreduce.Job:  map 72% reduce 0%
17/04/05 13:54:58 INFO mapreduce.Job:  map 75% reduce 0%
17/04/05 13:55:05 INFO mapreduce.Job:  map 78% reduce 0%
17/04/05 13:55:06 INFO mapreduce.Job:  map 84% reduce 0%
17/04/05 13:55:08 INFO mapreduce.Job:  map 88% reduce 0%
17/04/05 13:55:09 INFO mapreduce.Job:  map 97% reduce 0%
17/04/05 13:55:13 INFO mapreduce.Job:  map 100% reduce 0%
17/04/05 13:55:19 INFO mapreduce.Job:  map 100% reduce 17%
17/04/05 13:55:20 INFO mapreduce.Job:  map 100% reduce 33%
17/04/05 13:55:24 INFO mapreduce.Job:  map 100% reduce 50%
17/04/05 13:55:26 INFO mapreduce.Job:  map 100% reduce 67%
17/04/05 13:55:27 INFO mapreduce.Job:  map 100% reduce 100%
17/04/05 13:55:28 INFO mapreduce.Job: Job job_1491373381238_0002 completed successfully
17/04/05 13:55:28 INFO mapreduce.Job: Counters: 50

        File System Counters
                FILE: Number of bytes read=439893098
                FILE: Number of bytes written=878886691
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1000004800
                HDFS: Number of bytes written=1000000000
                HDFS: Number of read operations=114
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters 
                Launched map tasks=32
                Launched reduce tasks=6
                Data-local map tasks=30
                Rack-local map tasks=2
                Total time spent by all maps in occupied slots (ms)=317351
                Total time spent by all reduces in occupied slots (ms)=88680
                Total time spent by all map tasks (ms)=317351
                Total time spent by all reduce tasks (ms)=88680
                Total vcore-seconds taken by all map tasks=317351
                Total vcore-seconds taken by all reduce tasks=88680
                Total megabyte-seconds taken by all map tasks=324967424
                Total megabyte-seconds taken by all reduce tasks=90808320
        Map-Reduce Framework
                Map input records=10000000
                Map output records=10000000
                Map output bytes=1020000000
                Map output materialized bytes=434188707
                Input split bytes=4800
                Combine input records=0
                Combine output records=0
                Reduce input groups=10000000
                Reduce shuffle bytes=434188707
                Reduce input records=10000000
                Reduce output records=10000000
                Spilled Records=20000000
                Shuffled Maps =192
                Failed Shuffles=0
                Merged Map outputs=192
                GC time elapsed (ms)=6542
                CPU time spent (ms)=174530
                Physical memory (bytes) snapshot=19037917184
                Virtual memory (bytes) snapshot=60211707904
                Total committed heap usage (bytes)=21085814784
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters 
                Bytes Read=1000000000
        File Output Format Counters 
                Bytes Written=1000000000

17/04/05 13:55:28 INFO terasort.TeraSort: done
7.97user 0.35system 1:22.99elapsed 10%CPU (0avgtext+0avgdata 213364maxresident)k
0inputs+1896outputs (0major+67589minor)pagefaults 0swaps


```

# Times

- teragen:
	*5.83user 0.29system 0:27.39elapsed 22%CPU
- terasort
	*7.97user 0.35system 1:22.99elapsed 10%CPU (0avgtext+0avgdata 213364maxresident)