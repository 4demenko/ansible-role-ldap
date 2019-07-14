# ansible-role-openldap
Ansible OpenLDAP (slapd) role

The role: 
- install OpenLDAP server
- you can start repeatedly the role
- Add users and OU if you need. It's may very useful
- Enable TLS connection with your cert

Check 636 with TLS. Run the command on remote client:
openssl s_client -connect ldapserver.lab.example.com:636 -showcerts -state

If TLS work normaly, you get answer with msg: verify return code: 0 (ok)
If TLS doesn't work normaly, you get msg:certificate verify failed (self signed certificate).

Check anonymouse user
ldapwhoami -H ldap://ldapserver.lab.example.com -x -ZZ

Simple check TLS 
ldapwhoami -H ldap://ldapserver.lab.example.com -x -D "cn=admin,dc=lab,dc=example,dc=com" -W -ZZ
