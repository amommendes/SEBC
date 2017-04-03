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
[centos@ip-10-0-1-122 transparent_hugepage]$ sudo vi /etc/grub.conf

default=0
timeout=0
title CentOS Linux 7 (3.10.0-327.10.1.el7.x86_64)
        root (hd0)
        kernel /boot/vmlinuz-3.10.0-327.10.1.el7.x86_64 ro root=UUID=ef6ba050-6cdc-416a-9380-c14304d0d206 console=hvc0 LANG=en_US.UTF-8
        initrd /boot/initramfs-3.10.0-327.10.1.el7.x86_64.img
# I included this
transparent_hugepage=never

[centos@ip-10-0-1-122 transparent_hugepage]$ sudo vi /etc/grub.conf

touch /var/lock/subsys/local

if test -f
/sys/kernel/mm/transparent_hugepage/enabled; then
   echo never > /sys/kernel/mm/transparent_hugepage/enabled
fi
</code>



<code>
# Server
[centos@ip-10-0-1-122 ~]$ ip address
1: lo: LOOPBACK,UP,LOWER_UP mtu 65536 qdisc noqueue state UNKNOWN 
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:36:53:e7:fb:03 brd ff:ff:ff:ff:ff:ff
    inet 10.0.1.122/24 brd 10.0.1.255 scope global dynamic eth0
       valid_lft 3215sec preferred_lft 3215sec
    inet6 fe80::836:53ff:fee7:fb03/64 scope link 
       valid_lft forever preferred_lft forever
      
</code>
