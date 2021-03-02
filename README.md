# Setup and Configure OpenLDAP using Docker

 OpenLDAP + phpldapadmin (Docker / Docker Compose)
>   (kupadhyay1212@gmail.com)
>   

# OpenLDAP

###### Base Image:

```bash
osixia/openldap:latest
```

###### Port:

```bash
- "389:389"
- "636:636"
```

###### Volumes:

```bash
- /dockervolume/openldap/ldap:/var/lib/ldap
- /dockervolume/openldap/slapd.d:/etc/ldap/slapd.d
- /dockervolume/openldap/certificates:/container/service/slapd/assets/certs

```

###### Environment:

```bash
- LDAP_ORGANISATION=krishna
- LDAP_DOMAIN=krishna.com
- LDAP_ADMIN_USERNAME=admin
- LDAP_ADMIN_PASSWORD=test@123#
- LDAP_CONFIG_PASSWORD=config_pass
- "LDAP_BASE_DN=dc=krishna,dc=com"
- LDAP_TLS_CRT_FILENAME=server.crt
- LDAP_TLS_KEY_FILENAME=server.key
- LDAP_TLS_CA_CRT_FILENAME=krishna.com.ca.crt
- LDAP_READONLY_USER=true
- LDAP_READONLY_USER_USERNAME=amnil
- LDAP_READONLY_USER_PASSWORD=test123
```



#### phpLDAPadmin

###### Base Image:

```bash
osixia/phpldapadmin:latest
```

###### Port:

```bash
- "80:80"
```

###### Environment:

```bash
- PHPLDAPADMIN_LDAP_HOSTS=openldap
- PHPLDAPADMIN_HTTPS=false
```
 
