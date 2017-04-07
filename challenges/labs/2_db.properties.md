# Properties from CM Database

```
		
		[root@ip-10-0-1-197 cloudera-scm-server]# cat db.properties
		# Auto-generated by scm_prepare_database.sh on Fri Apr  7 17:26:42 UTC 2017
		#
		# For information describing how to configure the Cloudera Manager Server
		# to connect to databases, see the "Cloudera Manager Installation Guide."
		#
		com.cloudera.cmf.db.type=mysql
		com.cloudera.cmf.db.host=10.0.1.203
		com.cloudera.cmf.db.name=scm
		com.cloudera.cmf.db.user=scm
		com.cloudera.cmf.db.setupType=EXTERNAL
		com.cloudera.cmf.db.password=scm
		
```

# First line from Server Log

```
	
	[root@ip-10-0-1-197 cloudera-scm-server]# head -n1 /var/log/cloudera-scm-server/cloudera-scm-server.log
	
	2017-04-07 18:07:19,221 INFO WebServerImpl:org.springframework.web.servlet.mvc.annotation.DefaultAnnotationHandlerMapping: Mapped URL path [/services/{serviceId}/reports/historicalDiskUsage] onto handler 'reportsController'

```

# Jetty line

```
	
	[root@ip-10-0-1-197 cloudera-scm-server]# cat /var/log/cloudera-scm-server/cloudera-scm-server.log | grep Jetty
	
	2017-04-07 18:07:22,047 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.

	
```