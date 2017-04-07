# Challenges - Services Enablement Boot Camp - São Paulo - April 4 - 7, 2017

1. Cloud Provider:

### Amazon

2. IP address from instances:


|       Name          |   IP Public    |  IP Private  |                DNS Private               |
|---------------------|----------------|--------------|------------------------------------------|
|Master               | 54.207.107.68  |  10.0.1.203  | ip-10-0-1-203.sa-east-1.compute.internal |
|Utilities and Edge   | 54.233.136.235 |  10.0.1.197  | ip-10.0.1.197.sa-east-1.compute.internal |
|Worker 1             | 54.233.100.71  |  10.0.1.76   | ip-10.0.1.76.sa-east-1.compute.internal  |
|Worker 2             | 52.67.103.163  |  10.0.1.243  | ip-10.0.1.243.sa-east-1.compute.internal |
|Worker 3             | 54.233.195.215 |  10.0.1.126  | ip-10.0.1.126.sa-east-1.compute.internal|


3. OS Version

CentOS Linux 7 x86_64 
AMI: HVM EBS 1602-b7ee8a69-ee97-4a49-9e68-afaee216db2e-ami-d7e1d2bd.3 (ami-26b93b4a)


4. Listing Repos (Master Node)

I added the MariaDB and Cloudera-Manager Repo

``` 

[root@ip-10-0-1-203 yum.repos.d]# yum repolist enabled
Loaded plugins: fastestmirror

cloudera-manager                                                                                                                                           |  951 B  00:00:00     
mariadb                                                                                                                                                    | 2.9 kB  00:00:00     
mariadb/primary_db                                                                                                                                         |  18 kB  00:00:00     
cloudera-manager/primary                                                                                                                                   | 4.2 kB  00:00:00     
Loading mirror speeds from cached hostfile
 * base: centos.xpg.com.br
 * extras: centos.xpg.com.br
 * updates: centos.xpg.com.br
cloudera-manager                                                                                                                                                              8/8
repo id                                                                              repo name                                                                              status
base/7/x86_64                                                                        CentOS-7 - Base                                                                        9,363
cloudera-manager                                                                     Cloudera Manager                                                                           8
extras/7/x86_64                                                                      CentOS-7 - Extras                                                                        311
mariadb                                                                              MariaDB                                                                                   15
updates/7/x86_64                                                                     CentOS-7 - Updates                                                                     1,126
repolist: 10,823


```
Here I will use a local Parcels repo in the Master Node, with SimpleHTTPSever from python.

```

[root@ip-10-0-1-203 cloudera]# pwd

/home/centos/cloudera

[root@ip-10-0-1-203 cloudera]# cd cdh

[root@ip-10-0-1-203 cdh]# wget https://archive.cloudera.com/cdh5/parcels/5.10.1/

CDH-5.10.1-1.cdh5.10.1.p0.10-el7.parcel
--2017-04-07 13:26:03--  https://archive.cloudera.com/cdh5/parcels/5.10.1/CDH-5.10.1-1.cdh5.10.1.p0.10-el7.parcel
Resolving archive.cloudera.com (archive.cloudera.com)... 151.101.92.167
Connecting to archive.cloudera.com (archive.cloudera.com)|151.101.92.167|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1582619569 (1.5G)
Saving to: ‘CDH-5.10.1-1.cdh5.10.1.p0.10-el7.parcel’

100%[===================================================>] 1,582,619,569 42.4MB/s   in 41s    

2017-04-07 13:26:45 (36.7 MB/s) - ‘CDH-5.10.1-1.cdh5.10.1.p0.10-el7.parcel’ saved [1582619569/1582619569]


[root@ip-10-0-1-203 cdh]# wget https://archive.cloudera.com/cdh5/parcels/5.10.1/manifest.json

--2017-04-07 13:27:57--  https://archive.cloudera.com/cdh5/parcels/5.10.1/manifest.json

Resolving archive.cloudera.com (archive.cloudera.com)... 151.101.92.167

Connecting to archive.cloudera.com (archive.cloudera.com)|151.101.92.167|:443... connected.

HTTP request sent, awaiting response... 200 OK
Length: 65122 (64K) [application/json]
Saving to: ‘manifest.json’

100%[======================================================>] 65,122      --.-K/s   in 0.06s 

2017-04-07 13:27:57 (1.10 MB/s) - ‘manifest.json’ saved [65122/65122]

[root@ip-10-0-1-203 cdh]# python -m SimpleHTTPServer 80 &

[1] 9390

[root@ip-10-0-1-203 cloudera]# Serving HTTP on 0.0.0.0 port 80 ...

```


5. Creating users and groups:

```

[root@ip-10-0-1-203 cloudera]# groupadd barca && groupadd merengues

[root@ip-10-0-1-203 cloudera]# getent group | grep "\(merengues\)\|\(barca\)"

barca:x:1001:
merengues:x:1002:

[root@ip-10-0-1-203 cloudera]# adduser neymar -gmerengues -u2010
[root@ip-10-0-1-203 cloudera]# passwd neymar

Changing password for user neymar.
New password: 
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: 
passwd: all authentication tokens updated successfully.

[root@ip-10-0-1-203 cloudera]# adduser ronaldo -gbarca -u2016

[root@ip-10-0-1-203 cloudera]# passwd ronaldo
Changing password for user ronaldo.
New password: 
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: 
passwd: all authentication tokens updated successfully.


[root@ip-10-0-1-203 cloudera]# cat /etc/passwd | grep "\(neymar\)\|\(ronaldo\)"

neymar:x:2010:1002::/home/neymar:/bin/bash
ronaldo:x:2016:1001::/home/ronaldo:/bin/bash


[root@ip-10-0-1-203 cloudera]# getent group | grep "\(merengues\)\|\(barca\)"

barca:x:1001:
merengues:x:1002:


```


6. Pre install Reqs

 * Swappiness

```
 	[root@ip-10-0-1-203 cloudera]# cat /proc/sys/vm/swappiness

 			30

	[root@ip-10-0-1-203 cloudera]# sysctl -w vm.swappiness=1

		vm.swappiness = 1
	
	[root@ip-10-0-1-203 cloudera]# cat /proc/sys/vm/swappiness
	
 		1

```

 * Transparent Hugepage

```
	[root@ip-10-0-1-203 cloudera]#    echo never > /sys/kernel/mm/transparent_hugepage/enabled

	[root@ip-10-0-1-203 cloudera]#    echo never > /sys/kernel/mm/transparent_hugepage/defrag

	[root@ip-10-0-1-203 cloudera]# cat /sys/kernel/mm/transparent_hugepage/enabled 

	always madvise [never]

	[root@ip-10-0-1-203 cloudera]# cat /sys/kernel/mm/transparent_hugepage/defrag

	always madvise [never]

```

 * Mounting points

``` 

	 	[root@ip-10-0-1-203 ~]# fdisk /dev/xvdb
	
		[root@ip-10-0-1-203 ~]# mkfs.ext4 /dev/xvdb1
	
		[root@ip-10-0-1-203 ~]# mkdir /mnt/data1
	
		[root@ip-10-0-1-203 ~]# mount /dev/xvdb1 /mnt/data1/
	
		[root@ip-10-0-1-203 ~]# mount -o remount /mnt/data1/


```

 * NTP and NSCD installed and running

```
	
	[root@ip-10-0-1-203 ~]# systemctl status nscd
		● nscd.service - Name Service Cache Daemon
   		
   		Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   		
   		Active: active (running) since Fri 2017-04-07 14:20:18 UTC; 36s ago
  
  		Process: 16627 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 		
 		Main PID: 16628 (nscd)
   
   		CGroup: /system.slice/nscd.service
        		   └─16628 /usr/sbin/nscd

	[root@ip-10-0-1-203 ~]# systemctl status ntpd
		● ntpd.service - Network Time Service
   		
   		Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   
   		Active: active (running) since Fri 2017-04-07 14:20:01 UTC; 55s ago
  
  		Process: 16614 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
		
		Main PID: 16615 (ntpd)
		   CGroup: /system.slice/ntpd.service
		           └─16615 /usr/sbin/ntpd -u ntp:ntp -g

```

 * etc/hosts


	```

		127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
		::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
		10.0.1.203      ip-10-0-1-203.sa-east-1.compute.internal 
		10.0.1.197      ip-10.0.1.197.sa-east-1.compute.internal 
		10.0.1.76       ip-10.0.1.76.sa-east-1.compute.internal  
		10.0.1.243      ip-10.0.1.243.sa-east-1.compute.internal 
		10.0.1.126      ip-10.0.1.126.sa-east-1.compute.internal

	```
 * SELinux

```

	[root@ip-10-0-1-203 ~]#	vi /etc/selinux/config
	
	# This file controls the state of SELinux on the system.
	# SELINUX= can take one of these three values:
	#     enforcing - SELinux security policy is enforced.
	#     permissive - SELinux prints warnings instead of enforcing.
	#     disabled - No SELinux policy is loaded.
	SELINUX=disabled
	# SELINUXTYPE= can take one of three two values:
	#     targeted - Targeted processes are protected,
	#     minimum - Modification of targeted policy. Only selected processes are protected.
	#     mls - Multi Level Security protection.
	SELINUXTYPE=targeted
	
	[root@ip-10-0-1-203 ~]# setenforce 0


```

  