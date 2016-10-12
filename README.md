Role Name
=========

Requirements
------------

Debian 

Tested on Debian Jessie 

Role Variables
--------------

###Deployment Variables

* **openldap_server_domain_name** Sets the domain name in the fomrat of DOMAIN.TLD here this will be used as the base dn for your deployment and the DOMAIN part will be used as the samba domain.
* **openldap_server_rootpw** Sets password for cn=admin,dc=DOMAIN,DC=TLD
* **templatedir** is used as a location to place the templates after and during installation. 
* **openldap_server_app_path** is the Location of the slapd configuration directory useualy /etc/ldap/
* **openldap_server_user** is the user the slapd process runs as useual "openldap"
* **openldap_hostname** is theHostname for the Self generated SSL cert this is only used with openldap_generate_certs = true. 
* **openldap_generate_certs** ca be set to  true or false this is used to generate self signed certs if set to true and will copy - **files from files/certs/ when set to false.
* **openldap_certkey_name** will generate a cert key in /etc/ldap/certs/ or copy a key with the same name as this var from files/certs/
* **openldap_cert_name** will generate a cert in /etc/ldap/certs/ or copy a cert  with the same name as this var from files/certs/
* **openldap_ca_name** will copy a CA cert with this name from files/certs/ to /etc/ldap/certs/
* **samba_sid** please change a few numbers in the last 3 groups as this will be the sid for the Samba domain.

###The self signed ssl parameters
* **openldap_server_country** Sets the country code for the self signed cert.
* **openldap_server_state** Sets the state for the self signed cert.
* **openldap_server_location** Sets the location/city for the self signed cert.
* **openldap_server_organization** Sets the Company/Department for the self signed cert.


Dependencies
------------


Example Playbook
----------------

```
- hosts: ldap-servers

  vars:
    openldap_server_domain_name: test.local
    openldap_server_rootpw: Test123
    templatedir: /root/ldap/
    openldap_server_app_path: /etc/ldap/
    openldap_server_user: "openldap"
    openldap_hostname: "ldap.local"
    openldap_generate_certs: true

    openldap_certkey_name: "ldap.key"
    openldap_cert_name: "ldap.crt"
    openldap_ca_name: "sub.class1.server.ca.pem"

    #please change a few numbers in the last 3 groups
    samba_sid: "sambaSID: S-1-5-21-2919752157-891696647-4172528126"

    ##The self signed ssl parameters
    openldap_server_country: US
    openldap_server_state: oregon
    openldap_server_location: portland
    openldap_server_organization: IT
```


License
-------

Free to use for personal and commercial.

GPL

Author Information
------------------
Matthew Frost (Creator/Maintaniner) ansible@mattronix.nl


An optional section for the role authors to include contact information, or a website (HTML is not allowed).
