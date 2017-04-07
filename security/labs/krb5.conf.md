# Config krb5.conf

```

 vi /etc/krb5.conf 

# Configuration snippets may be placed in this directory as well
includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = SA-EAST-1.COMPUTE.INTERNAL 
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 rdns = false
 udp_preference_limit = 1
 default_ccache_name = KEYRING:persistent:%{uid}
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac

[realms]
 SA-EAST-1.COMPUTE.INTERNAL  = {
  kdc = ip-10-0-1-19.sa-east-1.compute.internal
  admin_server = ip-10-0-1-19.sa-east-1.compute.internal
 }


[domain_realm]
 .ip-10-0-1-19.sa-east-1.compute.internal = SA-EAST-1.COMPUTE.INTERNAL 
 ip-10-0-1-19.sa-east-1.compute.internal = SA-EAST-1.COMPUTE.INTERNAL 
 

 ```