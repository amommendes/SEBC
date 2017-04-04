# Installation and Replication Lab

## Installation

- This command will install MariaDB (5.5)

``` 
sudo yum install mariadb-server 

```

- my.cnf file from Master:


```

```

-Grants for slave user:


```
MariaDB [(none)]> show grants for 'slave'@'%' ;

| Grants for slave@%                                      |
|---------------------------------------------------------|
| GRANT REPLICATION SLAVE ON *.* TO 'slave'@'%' IDENTIFIED BY PASSWORD 'XXXX' |
```

