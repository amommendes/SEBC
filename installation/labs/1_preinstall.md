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

transparent_hugepage=never

[centos@ip-10-0-1-122 transparent_hugepage]$ sudo vi /etc/grub.conf

touch /var/lock/subsys/local

if test -f
/sys/kernel/mm/transparent_hugepage/enabled; then
   echo never > /sys/kernel/mm/transparent_hugepage/enabled
fi
</code>

5. List your network interface configuration


<code>
[centos@ip-10-0-1-122 ~]$ ip address
1: lo: LOOPBACK,UP,LOWER_UP mtu 65536 qdisc noqueue state UNKNOWN 
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: BROADCAST,MULTICAST,UP,LOWER_UP mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:36:53:e7:fb:03 brd ff:ff:ff:ff:ff:ff
    inet 10.0.1.122/24 brd 10.0.1.255 scope global dynamic eth0
       valid_lft 3494sec preferred_lft 3494sec
    inet6 fe80::836:53ff:fee7:fb03/64 scope link 
       valid_lft forever preferred_lft forever

</code>

6. Show correct forward and reverse host lookups

<code>

[centos@ip-10-0-1-37 etc]$ getent hosts  ip-10-0-1-122.sa-east-1.compute.internal
10.0.1.122      ip-10-0-1-122.sa-east-1.compute.internal

[centos@ip-10-0-1-122 ~]$ nslookup ip-10-0-1-122.sa-east-1.compute.internal
Server:         10.0.0.2
Address:        10.0.0.2#53

Non-authoritative answer:
Name:   ip-10-0-1-122.sa-east-1.compute.internal
Address: 10.0.1.122
</code>

7. Show the nscd service is running

<code>
[centos@ip-10-0-1-122 ~]$ sudo service nscd start
Redirecting to /bin/systemctl start  nscd.service
[centos@ip-10-0-1-122 ~]$ sudo service nscd status
Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Seg 2017-04-03 19:23:06 UTC; 4s ago
  Process: 2382 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 2383 (nscd)
   CGroup: /system.slice/nscd.service
           └─2383 /usr/sbin/nscd
</code>

8. Show the ntpd service is running

<code>
[centos@ip-10-0-1-122 ~]$ sudo service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Seg 2017-04-03 19:15:22 UTC; 9s ago
  Process: 2239 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 2240 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─2240 /usr/sbin/ntpd -u ntp:ntp -g

Abr 03 19:15:22 ip-10-0-1-122.sa-east-1.compute.internal ntpd[2240]: Listen norm...
Abr 03 19:15:22 ip-10-0-1-122.sa-east-1.compute.internal ntpd[2240]: Listen norm...
Abr 03 19:15:22 ip-10-0-1-122.sa-east-1.compute.internal ntpd[2240]: Listen norm...
Abr 03 19:15:22 ip-10-0-1-122.sa-east-1.compute.internal ntpd[2240]: Listen norm...
Abr 03 19:15:22 ip-10-0-1-122.sa-east-1.compute.internal ntpd[2240]: Listening o...
Abr 03 19:15:22 ip-10-0-1-122.sa-east-1.compute.internal systemd[1]: Started Net...
Abr 03 19:15:22 ip-10-0-1-122.sa-east-1.compute.internal ntpd[2240]: 0.0.0.0 c01...
Abr 03 19:15:22 ip-10-0-1-122.sa-east-1.compute.internal ntpd[2240]: 0.0.0.0 c01...
Abr 03 19:15:22 ip-10-0-1-122.sa-east-1.compute.internal ntpd[2240]: 0.0.0.0 c01...
Abr 03 19:15:29 ip-10-0-1-122.sa-east-1.compute.internal ntpd[2240]: 0.0.0.0 c61...
Hint: Some lines were ellipsized, use -l to show in full.
</code>

#MySQL/MariaDB Installation Lab
-Commands

<code>

sudo yum install mariadb
sudo vi /etc/my.cnf
[mysqld]
transaction-isolation = READ-COMMITTED
# Disabling symbolic-links is recommended to prevent assorted security risks;
# to do so, uncomment this line:
# symbolic-links = 0

key_buffer = 16M
key_buffer_size = 32M
max_allowed_packet = 32M
thread_stack = 256K
thread_cache_size = 64
query_cache_limit = 8M
query_cache_size = 64M
query_cache_type = 1

max_connections = 550
#expire_logs_days = 10
#max_binlog_size = 100M

#log_bin should be on a disk with enough free space. Replace '/var/lib/mysql/mysql_binary_log' with an appropriate path for your system
#and chown the specified folder to the mysql user.
log_bin=/var/lib/mysql/mysql_binary_log

binlog_format = mixed

read_buffer_size = 2M
read_rnd_buffer_size = 16M
sort_buffer_size = 8M
join_buffer_size = 8M

# InnoDB settings
innodb_file_per_table = 1
innodb_flush_log_at_trx_commit  = 2
innodb_log_buffer_size = 64M
innodb_buffer_pool_size = 4G
innodb_thread_concurrency = 8
innodb_flush_method = O_DIRECT
innodb_log_file_size = 512M

[mysqld_safe]
log-error=/var/log/mariadb/mariadb.log
pid-file=/var/run/mariadb/mariadb.pid

</code>
