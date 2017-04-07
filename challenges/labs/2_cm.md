# Repo Files

```

	[root@ip-10-0-1-197 ~]# ls /etc/yum.repos.d
	CentOS-Base.repo       CentOS-fasttrack.repo  CentOS-Vault.repo      epel-testing.repo
	CentOS-CR.repo         CentOS-Media.repo      cloudera-manager.repo  MariaDB.repo
	CentOS-Debuginfo.repo  CentOS-Sources.repo    epel.repo

```

# Prepare Remote Database to Cloudera Manager

```
	
	[root@ip-10-0-1-197 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -h10.0.1.203 -uroot -proot --scm-host 10.0.1.197 scm scm scm -vf


```