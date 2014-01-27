# Oracle for Ansible

This role downloads, installs and configures Oracle Database 11g Release 2 for
CentOS 6. The included tasks are a rough port of an internal shell script, which
was itself a rough port of Oracle's installation instructions and
recommendations.

## Requirements

- CentOS 6.4+
- Ansible 1.4
- Oracle Database 11gR2 [installation content](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/112010-linx8664soft-100572.html)

## Variables

See the [default variables](defaults/main.yml), which are extensively
commented.

## Example

```yaml
---
- name: set up an oracle database
  sudo: yes
  vars:
    oracle_path: /u01/app       # ORACLE_BASE will be /u01/app/oracle
    oracle_db_name: my_special_db   # ORACLE_SID will be my_special_db
    oracle_db_home: special_home    # ORACLE_HOME will be /u01/app/oracle/product/11.2.0/special_home
    oracle_db_user: devuser
    oracle_db_pass: AnAwesomeAndAmazingP4ssw0rd
    oracle_db_syspass: AMor3AwesomeAndAmazingP4ssw0rd
    oracle_installer_uri: http://my.host # Ansible will download http://my.host/linux.x64_11gR2_database_1of2.zip
  roles:
    # more roles here
    - oracle
```
