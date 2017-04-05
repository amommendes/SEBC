# Results

1. 2 Mappers and 2 Reducers with 1024 mb

```

[centos@ip-10-0-1-248 ~]$ cat tera_2_2_1024.out
Spent 130ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 133ms
Sampling 8 splits of 8
Making 2 from 100000 sampled records
Computing parititions took 724ms
Spent 859ms computing partitions.

```

2. 2 Mappers and 2 Reducers with 512 mb

```

Spent 131ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 134ms
Sampling 8 splits of 8
Making 2 from 100000 sampled records
Computing parititions took 700ms
Spent 836ms computing partitions.



```

3. 4 Mappers 2 Reducers 512 mb

```

Spent 131ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 134ms
Sampling 8 splits of 8
Making 2 from 100000 sampled records
Computing parititions took 745ms
Spent 881ms computing partitions.

```
4. 4 Mappers 2 Reducers 1024 mb

```

Spent 129ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 132ms
Sampling 8 splits of 8
Making 2 from 100000 sampled records
Computing parititions took 645ms
Spent 779ms computing partitions.


```

5. 4 Mappers 2 Reducers 6144 mb

```

Spent 129ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 132ms
Sampling 8 splits of 8
Making 2 from 100000 sampled records
Computing parititions took 763ms
Spent 898ms computing partitions.

```