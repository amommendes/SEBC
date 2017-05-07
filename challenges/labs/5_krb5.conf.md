[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = AMOMMENDES.ES
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 udp_preference_limit = 1
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac 
[realms]
 AMOMMENDES.ES = {
  kdc = cloudera-2.c.cloudera-165315.internal
  admin_server = cloudera-2.c.cloudera-165315.internal

 }

[domain_realm]
 .c.cloudera-165315.internal = AMOMMENDES.ES 
 c.cloudera-165315.internal = AMOMMENDES.ES