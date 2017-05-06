# User directories

```

	[root@cloudera-2 ~]# hdfs dfs -ls /user
	Found 6 items
	drwxrwxrwx   - mapred hadoop              0 2017-05-06 21:21 /user/history
	drwxrwxr-t   - hive   hive                0 2017-05-06 21:22 /user/hive
	drwxrwxr-x   - hue    hue                 0 2017-05-06 21:23 /user/hue
	drwxr-xr-x   - hdfs   supergroup          0 2017-05-06 21:32 /user/neymar
	drwxrwxr-x   - oozie  oozie               0 2017-05-06 21:23 /user/oozie
	drwxr-xr-x   - hdfs   supergroup          0 2017-05-06 21:32 /user/ronaldo

```
# CM API Call

```

	[root@cloudera-2 ~]#  curl -u "admin:admin" -i http://104.154.231.76:7180/api/v11/hosts/
	HTTP/1.1 200 OK
	Expires: Thu, 01-Jan-1970 00:00:00 GMT
	Set-Cookie: CLOUDERA_MANAGER_SESSIONID=1x584bhzlt1s919m2owmf9zipy;Path=/;HttpOnly
	Content-Type: application/json
	Date: Sat, 06 May 2017 21:29:50 GMT
	Transfer-Encoding: chunked
	Server: Jetty(6.1.26.cloudera.4)

	{
	  "items" : [ {
	    "hostId" : "c45a8ffa-139b-4d09-a6b1-c5e4d146a533",
	[root@cloudera-2 ~]#  curl -u "admin:admin" -i http://104.154.231.76:7180/api/v11/hosts/
	HTTP/1.1 200 OK
	Expires: Thu, 01-Jan-1970 00:00:00 GMT
	Set-Cookie: CLOUDERA_MANAGER_SESSIONID=1dsdelpolrc203zwav2mu9l2m;Path=/;HttpOnly
	Content-Type: application/json
	Date: Sat, 06 May 2017 21:30:02 GMT
	Transfer-Encoding: chunked
	Server: Jetty(6.1.26.cloudera.4)

	{
	  "items" : [ {
	    "hostId" : "c45a8ffa-139b-4d09-a6b1-c5e4d146a533",
	    "ipAddress" : "10.128.0.2",
	    "hostname" : "cloudera-1.c.cloudera-165315.internal",
	    "rackId" : "/default",
	    "hostUrl" : "http://cloudera-2.c.cloudera-165315.internal:7180/cmf/hostRedirect/c45a8ffa-139b-4d09-a6b1-c5e4d146a533",
	    "maintenanceMode" : false,
	    "maintenanceOwners" : [ ],
	    "commissionState" : "COMMISSIONED",
	    "numCores" : 2,
	    "numPhysicalCores" : 1,
	    "totalPhysMemBytes" : 13685518336
	  }, {
	    "hostId" : "cffdcddc-dc8f-449a-a8d3-7a81708dbcb8",
	    "ipAddress" : "10.128.0.3",
	    "hostname" : "cloudera-2.c.cloudera-165315.internal",
	    "rackId" : "/default",
	    "hostUrl" : "http://cloudera-2.c.cloudera-165315.internal:7180/cmf/hostRedirect/cffdcddc-dc8f-449a-a8d3-7a81708dbcb8",
	    "maintenanceMode" : false,
	    "maintenanceOwners" : [ ],
	    "commissionState" : "COMMISSIONED",
	    "numCores" : 2,
	    "numPhysicalCores" : 1,
	    "totalPhysMemBytes" : 13685518336
	  }, {
	    "hostId" : "ead9eeea-fcf1-4099-8d17-45a6caaee37e",
	    "ipAddress" : "10.128.0.4",
	    "hostname" : "cloudera-3.c.cloudera-165315.internal",
	    "rackId" : "/default",
	    "hostUrl" : "http://cloudera-2.c.cloudera-165315.internal:7180/cmf/hostRedirect/ead9eeea-fcf1-4099-8d17-45a6caaee37e",
	    "maintenanceMode" : false,
	    "maintenanceOwners" : [ ],
	    "commissionState" : "COMMISSIONED",
	    "numCores" : 2,
	    "numPhysicalCores" : 1,
	    "totalPhysMemBytes" : 13685518336
	  }, {
	    "hostId" : "9ee14da6-1fc2-432a-b934-672d66ca2b34",
	    "ipAddress" : "10.128.0.5",
	    "hostname" : "cloudera-4.c.cloudera-165315.internal",
	    "rackId" : "/default",
	    "hostUrl" : "http://cloudera-2.c.cloudera-165315.internal:7180/cmf/hostRedirect/9ee14da6-1fc2-432a-b934-672d66ca2b34",
	    "maintenanceMode" : false,
	    "maintenanceOwners" : [ ],
	    "commissionState" : "COMMISSIONED",
	    "numCores" : 2,
	    "numPhysicalCores" : 1,
	    "totalPhysMemBytes" : 13685518336
	  } ]

```