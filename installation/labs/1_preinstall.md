# Preinstall Reqs
1. Check vm.swappiness on all your nodes
    
    <code>
    [centos@ip-10-0-1-122 vm]$ cat /proc/sys/vm/swappiness
       30
    [centos@ip-10-0-1-122 etc]$ sudo sysctl -w vm.swappiness=1
	vm.swappiness = 1
    [centos@ip-10-0-1-122 etc]$ cat /proc/sys/vm/swappiness 
        1
    </code>
  2.Show the mount attributes of your volume(s)
  
  <code>
	[centos@ip-10-0-1-122 etc]$ lsblk
	NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
		xvda    202:0    0  40G  0 disk 
		└─xvda1 202:1    0  40G  0 part /
		xvdb    202:16   0  40G  0 disk
  </code>
  
  3. If you have ext-based volumes, list the reserve space setting
	
<code>
	[centos@ip-10-0-1-122 data01]$ df -h
		Filesystem      Size  Used Avail Use% Mounted on
		/dev/xvda1       40G  940M   40G   3% /
		devtmpfs        7,3G     0  7,3G   0% /dev
		tmpfs           7,2G     0  7,2G   0% /dev/shm
		tmpfs           7,2G   17M  7,2G   1% /run
		tmpfs           7,2G     0  7,2G   0% /sys/fs/cgroup
		tmpfs           1,5G     0  1,5G   0% /run/user/1000
		tmpfs           1,5G     0  1,5G   0% /run/user/0
	[centos@ip-10-0-1-122 data01]$ df /
		Filesystem     1K-blocks   Used Available Use% Mounted on
		/dev/xvda1      41926416 962236  40964180   3% /
</code>

4. List your network interface configuration

<code>
[centos@ip-10-0-1-122 transparent_hugepage]$ cat /sys/kernel/mm/transparent_hugepage/enabled 
[always] madvise never
</code>
