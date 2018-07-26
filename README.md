[![Build Status](https://img.shields.io/travis/ptavares/ansible-role-manage-system/master.svg?style=flat-square)](https://travis-ci.org/ptavares/ansible-role-manage-system)
[![Ansible Role](https://img.shields.io/ansible/role/27842.svg)](https://galaxy.ansible.com/ptavares/ansible-role-manage-system)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/ptavares/ansible-role-manage-system/blob/master/LICENSE)

ansible-role-mange-system
=========

Ansible role for managing system system (update - install/remove packages - clean)

Requirements
------------

Only tested with ansible 2.5 min version

Role Variables
--------------
- Copy content of [main.yml]()
- Customize it as you like, following as below :
```yaml
---
###############################
# Section for system updates
##############################
# Wether or not call update-system task
system_update: false
# Whether or not only applies security updates
system_update_security_only: false

###################################
# Section for install/remove package
####################################
# -----------------------------------
# Common to Debian/Ubuntu/Centos/RHEL
# -----------------------------------
# Packages to install
system_packages_install:
  - wget
  - curl
  - vim
  - p7zip-full
  - p7zip-rar
  - dos2unix
  - network-manager
  - network-manager-openvpn
  - jq
  - python
  - python-pip
  - jmtpfs
  - dar

# Package to remove
system_packages_remove:
  - light-locker
  - nano

# ----------------------
# Specific Debian/Ubuntu
# ----------------------
# system_deb_urls:
#  - "https://prerelease.keybase.io/keybase_amd64.deb"

# --------------------
# Specific Centos/RHEL
# --------------------
# system_rpm_urls:
#  - "https://prerelease.keybase.io/keybase_amd64.rpm"

###############################
# Section for system clean
##############################
# Wether or not call clean-system task
system_clean: true
```

Dependencies
------------

No dependencie

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ptavares.ansible_role_mange_system }

License
-------

MIT
