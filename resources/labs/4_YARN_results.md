# Results

1. 4 Mappers 2 Reducers 512 mb

```

Spent 131ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 134ms
Sampling 8 splits of 8
Making 2 from 100000 sampled records
Computing parititions took 745ms
Spent 881ms computing partitions.

7.81user 0.35system 0:52.97elapsed 15%CPU (0avgtext+0avgdata 202244maxresident)k
0inputs+1040outputs (0major+64749minor)pagefaults 0swaps

```
2. 4 Mappers 2 Reducers 1024 mb

```

Spent 129ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 132ms
Sampling 8 splits of 8
Making 2 from 100000 sampled records
Computing parititions took 645ms
Spent 779ms computing partitions.

7.87user 0.32system 0:48.95elapsed 16%CPU (0avgtext+0avgdata 197164maxresident)k
0inputs+1040outputs (0major+63773minor)pagefaults 0swaps

```

3. 4 Mappers 2 Reducers 6144 mb

```

Spent 129ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 132ms
Sampling 8 splits of 8
Making 2 from 100000 sampled records
Computing parititions took 763ms
Spent 898ms computing partitions.

3.59user 0.20system 0:02.55elapsed 148%CPU (0avgtext+0avgdata 148792maxresident)k
0inputs+976outputs (0major+49429minor)pagefaults 0swaps

```