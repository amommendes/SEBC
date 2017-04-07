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
    [root@ip-10-0-1-104 ~]# lsblk
    NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
    xvda    202:0    0  40G  0 disk 
    └─xvda1 202:1    0  40G  0 part /
    xvdb    202:16   0  40G  0 disk 
    └─xvdb1 202:17   0  40G  0 part /mnt/data1  
  </code>
  
  
3. If you have ext-based volumes, list the reserve space setting
	
	
<code>
    [root@ip-10-0-1-104 ~]# df -h
    Filesystem      Size  Used Avail Use% Mounted on
    /dev/xvda1       40G  1.7G   39G   5% /
    devtmpfs        7.3G     0  7.3G   0% /dev
    tmpfs           7.2G     0  7.2G   0% /dev/shm
    tmpfs           7.2G   17M  7.2G   1% /run
    tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
    cm_processes    7.2G  636K  7.2G   1% /run/cloudera-scm-agent/process
    tmpfs           1.5G     0  1.5G   0% /run/user/1000
    /dev/xvdb1       40G   49M   38G   1% /mnt/data1
</code>

4. Disable transparent hugepage support

<code>
[root@ip-10-0-1-104 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled 

[always] madvise never

   echo never > /sys/kernel/mm/transparent_hugepage/enabled
   echo never > /sys/kernel/mm/transparent_hugepage/defrag

[root@ip-10-0-1-104 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled 

always madvise [never]

[root@ip-10-0-1-104 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled 

always madvise [never]
</code>


5. List your network interface configuration


<code>
[root@ip-10-0-1-104 ~]# ip address
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN 
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:72:8d:d7:34:9f brd ff:ff:ff:ff:ff:ff
    inet 10.0.1.104/24 brd 10.0.1.255 scope global dynamic eth0
       valid_lft 2930sec preferred_lft 2930sec
    inet6 fe80::872:8dff:fed7:349f/64 scope link 
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
[root@ip-10-0-1-104 ~]# sudo service nscd start

Redirecting to /bin/systemctl start  nscd.service

[root@ip-10-0-1-104 ~]# sudo service nscd status

Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: active (running) since Wed 2017-04-05 02:18:32 UTC; 15s ago
  Process: 19438 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 19439 (nscd)
   CGroup: /system.slice/nscd.service
           └─19439 /usr/sbin/nscd
           
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

</code>
