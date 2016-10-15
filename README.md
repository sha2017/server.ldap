Role Name
=========

Requirements
------------

Debian 

Tested on Debian Jessie 

Role Variables
--------------

###Deployment Variables

- hosts: ldap-servers

  vars:
    openldap_:
      domain_name: "weho.st" Sets the domain name in the fomrat of DOMAIN.LOCAL here this will be used as the base dn for your deployment and the DOMAIN part will be used as the samba domain.
      domain_base: "dc=domain,dc=local" Sets the search domain for ldap.
      rootpw: "12345678" Sets password for cn=admin,dc=domain,DC=local
      user_read_password: "12345678" Used for Freeradius.
      uri: "ldap://ldap1.domain.local/" Sets the URI for finding LDAP servers.
      binduser: "cn=admin,dc=domain,dc=local" Used for linking workstations to LDAP.
      bindpw: "12345678" Used for linking workstations to LDAP.
      ssl: False Enables ssl in LDAP.
      tls_cacert: "/etc/ssl/certs/ca-certificates.crt" Used to set cacert for ldap.conf file.
      samba_sid: S-1-5-21-4939364547-892423455-2297369441 Sets samba sid for samba domain.
      


Dependencies
------------


Example Playbook
----------------

```


License
-------

Free to use for personal and commercial.

GPL

Author Information
------------------
Matthew Frost (Creator/Maintaniner) ansible@mattronix.nl


An optional section for the role authors to include contact information, or a website (HTML is not allowed).
