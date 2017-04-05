{
  "timestamp" : "2017-04-05T22:04:53.532Z",
  "clusters" : [ {
    "name" : "SEBC",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn,/mnt/data1/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "4293264998"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/mnt/data1/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn,/mnt/data1/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "ebAStdBGq9fpcm9P3ZvfFuVxcMosJz"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "5zphsplkJ1bhLvMl1i3muqv3LO0f9r"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "iarE4yMcP8p0TwkdnHZfPnZzPDpPUJ"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-a3c5821e7d105063c549f244ef83df6a",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "19a8b553-2be7-44e4-b4b3-9cfaf36f387c"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-2274fad8f2324d2a3a313926c8e2f038",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "dafa1091-8f78-4535-ab98-52768d2aa85b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9qzbmh0phgdk6brt377y35f1y"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-3932fb4b66cb5e7716557ea87576590f",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "e8aba220-9305-48e7-adc2-81323394ab9b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "45ie990lgz1az4bhze0v546a2"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-86fe73e7e65c7b8ce9fd02a185d7b584",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "7299838b-db7e-4270-97f8-f7d5814963c0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "er4c2wpodj7d37ochljh3o2v0"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-7484848f6ec70fe4e058f369dd90d0ca",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7auvqkmik96ad23o2y815czbc"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-a3c5821e7d105063c549f244ef83df6a",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "19a8b553-2be7-44e4-b4b3-9cfaf36f387c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1c6f6f441nzpwcvelgvo6h6ni"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-3932fb4b66cb5e7716557ea87576590f",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "e8aba220-9305-48e7-adc2-81323394ab9b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cl6q48nrfzo4tp3wm502j2scw"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-7484848f6ec70fe4e058f369dd90d0ca",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "etxnlkz4rnj8pxh827vzm496h"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-a3c5821e7d105063c549f244ef83df6a",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "19a8b553-2be7-44e4-b4b3-9cfaf36f387c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9m05jjuyuzeih19s0iuonizjl"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-7484848f6ec70fe4e058f369dd90d0ca",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "25"
          }, {
            "name" : "role_jceks_password",
            "value" : "dbfbujf1l1pefk0jr4bdqzytw"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-a3c5821e7d105063c549f244ef83df6a",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "19a8b553-2be7-44e4-b4b3-9cfaf36f387c"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "62"
          }, {
            "name" : "role_jceks_password",
            "value" : "52w8z16wgrcu81b2no0qld0ah"
          } ]
        }
      }, {
        "name" : "hdfs-NFSGATEWAY-a3c5821e7d105063c549f244ef83df6a",
        "type" : "NFSGATEWAY",
        "hostRef" : {
          "hostId" : "19a8b553-2be7-44e4-b4b3-9cfaf36f387c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1gds4a8wtikdnx5d4fuo27prv"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-3932fb4b66cb5e7716557ea87576590f",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "e8aba220-9305-48e7-adc2-81323394ab9b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cjek4f6t56qs8vw7mby1hy958"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-7484848f6ec70fe4e058f369dd90d0ca",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6ji8gxdi8jx7ncww79duud01z"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-a3c5821e7d105063c549f244ef83df6a",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "19a8b553-2be7-44e4-b4b3-9cfaf36f387c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4e3wts3fdtgs234qdahiuzarq"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "node_manager_java_heapsize",
            "value" : "52428800"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm,/mnt/data1/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs,/mnt/data1/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "1024"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4939"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "8BUzi4s8djMSLImY6PURK9TmoU36yn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-7484848f6ec70fe4e058f369dd90d0ca",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3dq3vqocc2q9j0fkrf7e59scq"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2274fad8f2324d2a3a313926c8e2f038",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "dafa1091-8f78-4535-ab98-52768d2aa85b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1bno7iz9qweg51g1zzdpl21xa"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-3932fb4b66cb5e7716557ea87576590f",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "e8aba220-9305-48e7-adc2-81323394ab9b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "x8pmqalup31hrjadopiq5fd0"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-86fe73e7e65c7b8ce9fd02a185d7b584",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "7299838b-db7e-4270-97f8-f7d5814963c0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "en7ri4sghp9n1zcf21zshv6jl"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-7484848f6ec70fe4e058f369dd90d0ca",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "45"
          }, {
            "name" : "role_jceks_password",
            "value" : "6481fgsqk9d59nuwao8ha8dko"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "959447040"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "959447040"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "912680550"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "153"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-10-0-1-19.sa-east-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "metastore"
        }, {
          "name" : "hive_metastore_database_user",
          "value" : "metastore"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-a3c5821e7d105063c549f244ef83df6a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "19a8b553-2be7-44e4-b4b3-9cfaf36f387c"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-7484848f6ec70fe4e058f369dd90d0ca",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3rhvbhhbwtv69rennvur82m95"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-7484848f6ec70fe4e058f369dd90d0ca",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bb3gxdus7cle1314kcy8tvnhc"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-10-0-1-19.sa-east-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "52428800"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-7484848f6ec70fe4e058f369dd90d0ca",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3yziegwhgvc81kzqe0dqs9tmy"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-10-0-1-19.sa-east-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-7484848f6ec70fe4e058f369dd90d0ca"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-2274fad8f2324d2a3a313926c8e2f038",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "dafa1091-8f78-4535-ab98-52768d2aa85b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "evdf0vomwibe8upn1lvuqlgnn"
          }, {
            "name" : "secret_key",
            "value" : "U1sfO3aVJ86aQz9sKz1Xit2D3xV456"
          } ]
        }
      } ],
      "displayName" : "Hue"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "dafa1091-8f78-4535-ab98-52768d2aa85b",
    "ipAddress" : "10.0.1.104",
    "hostname" : "ip-10-0-1-104.sa-east-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "1eeb9f70-621e-4a4f-a876-563db5b58f63",
    "ipAddress" : "10.0.1.19",
    "hostname" : "ip-10-0-1-19.sa-east-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "7299838b-db7e-4270-97f8-f7d5814963c0",
    "ipAddress" : "10.0.1.219",
    "hostname" : "ip-10-0-1-219.sa-east-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "19a8b553-2be7-44e4-b4b3-9cfaf36f387c",
    "ipAddress" : "10.0.1.248",
    "hostname" : "ip-10-0-1-248.sa-east-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "e8aba220-9305-48e7-adc2-81323394ab9b",
    "ipAddress" : "10.0.1.37",
    "hostname" : "ip-10-0-1-37.sa-east-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-2274fad8f2324d2a3a313926c8e2f038",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "13555f5f21fed04d439adfaa80e240d44359b9554629f88b237af3da8df47353",
    "pwSalt" : 1757174189770844449,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-2274fad8f2324d2a3a313926c8e2f038",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "118bcd9a5dac26fd6b5b1b6a48be63f304d0878ce069ad12f84d965548dafaed",
    "pwSalt" : -8460306547931570250,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-2274fad8f2324d2a3a313926c8e2f038",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3b4a4978bf8e5445f1827efb2311476e63cc568744a02ba3236a0de4f920329e",
    "pwSalt" : -7341243834104173754,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-2274fad8f2324d2a3a313926c8e2f038",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "877a870e81e0d1e8522d5380a2dbd704bc66ca53d581cf4697c22610a6b8fad1",
    "pwSalt" : -4363679859842316208,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "1f7769b1dcdb38d776311b7f960312df700f9f795818d3e4c68970df5144e167",
    "pwSalt" : -4889821084713554364,
    "pwLogin" : true
  }, {
    "name" : "amommendes",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "9b3b96fec08b9ba38b1e3e943da805fd718cf21845cb33284358bd87a1918af7",
    "pwSalt" : 4067429602385235869,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "6e4ceaa4cbb1c6f0457ca0821a7d7bbfb05adb221e5d4fd56c942bdb8bb057dd",
    "pwSalt" : -7791524514838306593,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.10.1",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170319-2001",
    "gitHash" : "f226435f6fa5f545543c00245900ae43bea7a29c",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-10-0-1-19.sa-east-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-2274fad8f2324d2a3a313926c8e2f038",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "dafa1091-8f78-4535-ab98-52768d2aa85b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "luqz5lt2pe28xmg56w42a24m"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-2274fad8f2324d2a3a313926c8e2f038",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "dafa1091-8f78-4535-ab98-52768d2aa85b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1e0n713c8ljbc05529i82rvgx"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-2274fad8f2324d2a3a313926c8e2f038",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "dafa1091-8f78-4535-ab98-52768d2aa85b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "79uniliqt5nz1r543e0btyefp"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-2274fad8f2324d2a3a313926c8e2f038",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "dafa1091-8f78-4535-ab98-52768d2aa85b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "83shfobwhlogvuhedwrki8p2b"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-2274fad8f2324d2a3a313926c8e2f038",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "dafa1091-8f78-4535-ab98-52768d2aa85b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7tcffsqf24nlgq94lkoctl8ll"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/24/2012 8:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://ip-10-0-1-19.sa-east-1.compute.internal/cdh5/,https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}