# Challenges - Services Enablement Boot Camp - São Paulo - May 6, 2017

1. Cloud Provider:

### Google Cloud Plataform

2. IP address from instances:


|       Name          |   IP Public    |  IP Private  |                DNS Private               |
|---------------------|----------------|--------------|------------------------------------------|
|cloudera-1           | 104.197.117.191|  10.128.0.2  | cloudera-1.c.cloudera-165315.intenral    |
|cloudera-2           | 104.154.231.76 |  10.128.0.3  | cloudera-2.c.cloudera-165315.intenral    |
|cloudera-3           | 35.184.105.111 |  10.128.0.4  | cloudera-3.c.cloudera-165315.intenral    |
|cloudera-4           | 104.154.133.151|  10.128.0.5  | cloudera-4.c.cloudera-165315.intenral    |


3. OS Version

CentOS release 6.9 (Final)

4. Listing Repos (Master Node)

I added the MariaDB and Cloudera-Manager Repo

``` 

yum repolist enabled
Loaded plugins: fastestmirror, security
Loading mirror speeds from cached hostfile
 * base: ftpmirror.your.org
 * epel: mirror.steadfast.net
 * extras: lug.mtu.edu
 * updates: mirror.team-cymru.org
cloudera-manager                                                                                                                                           |  951 B     00:00     
cloudera-manager/primary                                                                                                                                   | 4.3 kB     00:00     
cloudera-manager                                                                                                                                                              7/7
repo id                                  repo name                                                     status
base                                    CentOS-6 - Base                                                6,706
centos-sclo-rh                          CentOS-6 - SCLo rh                                             4,955
centos-sclo-sclo                        CentOS-6 - SCLo sclo                                           289
cloudera-manager                        Cloudera Manager                                               7
epel                                    Extra Packages for Enterprise Linux 6 - x86_64                 12,324
extras                                  CentOS-6 - Extras                                              64
google-cloud-compute                    Google Cloud Compute                                           4
updates                                 CentOS-6 - Updates                                             252
repolist: 24,601

```
5. Creating users and groups:

```

groupadd barca && groupadd merengues

getent group | grep "\(merengues\)\|\(barca\)"

barca:x:502:
merengues:x:503:

adduser neymar -gmerengues -u2010
passwd neymar

Changing password for user neymar.
New password: neymar
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: neymar 
passwd: all authentication tokens updated successfully.

adduser ronaldo -gbarca -u2016

passwd ronaldo
Changing password for user ronaldo.
New password: ronaldo 
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: ronaldo
passwd: all authentication tokens updated successfully.


cat /etc/passwd | grep "\(neymar\)\|\(ronaldo\)"

neymar:x:2010:503::/home/neymar:/bin/bash
ronaldo:x:2016:502::/home/ronaldo:/bin/bash

getent group | grep "\(merengues\)\|\(barca\)"

barca:x:502:
merengues:x:503:

```


6. Pre install Reqs

 * Swappiness

```
cat /proc/sys/vm/swappiness
 			1

```

 * Transparent Hugepage

```
    
    cat /sys/kernel/mm/transparent_hugepage/enabled 

	always madvise [never]

	cat /sys/kernel/mm/transparent_hugepage/defrag

	always madvise [never]

```

 * Mounting points

``` 

	 	fdisk /dev/sdb
	
		mkfs.ext4 /dev/sdb1
	
		mkdir /mnt/data1
	
		mount /dev/sdb1 /mnt/data1/
	
		mount -o remount /mnt/data1/

```

 * RPCBIND (used by NFSGateway) NTP and NSCD installed and running

```

	[root@cloudera-1 yum.repos.d]# service rpcbind status && service ntpd status && service nscd status
	rpcbind (pid  2105) is running...
	ntpd (pid  1566) is running...
	nscd (pid 1774) is running...

```

 * SELinux

```

	perl -pi -e 's/SELINUX=enforcing/SELINUX=disabled/' /etc/selinux/config
	setenforce 0


```
 * Hostname
 	Added FQDN to HOSTNAME in each host

```
	
	[root@cloudera-1 yum.repos.d]# cat /etc/sysconfig/network
	NETWORKING=yes
	HOSTNAME=cloudera-1.c.cloudera-165315.internal
	[root@cloudera-1 yum.repos.d]# hostname $(hostname -f)
	[root@cloudera-1 yum.repos.d]# hostname
	cloudera-1.c.cloudera-165315.internal
	

```

 * Firewall and iptables

```
	
	[root@cloudera-1 yum.repos.d]# service iptables status
	iptables: Firewall is not running.
``` 


  * /etc/hosts


```

	[root@cloudera-1 ~]# cat /etc/hosts
	127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
	::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
	10.128.0.2  cloudera-1.c.cloudera-165315.internal  cloudera-1
	10.128.0.3  cloudera-2.c.cloudera-165315.internal  cloudera-2
	10.128.0.4  cloudera-3.c.cloudera-165315.internal  cloudera-3
	10.128.0.5  cloudera-4.c.cloudera-165315.internal  cloudera-4
	169.254.169.254 metadata.google.internal  # Added by Google

```
