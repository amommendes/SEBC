# OS Memory

Formula changed to WorkerRam * 0.065 to get the minimum to OS (8 GB)
Following the spreadsheet, the mapreduce.reduce/map.java.opts.max.heap must be within 90% and 100%, in order to not waste memory.

# Workloads

The workload factor is affected by number of cores and memory available to each map/reduce tasks.
It represents the number of mappers/reducers some application can run.
1 means that each node can run with 1 mapper/reducer.
2 means that each node can run with 2 mappers/reducers.
4 means that each node can run with 4 mappers/reducers.


