[![Build Status](https://img.shields.io/travis/ptavares/ansible-role-manage-system/master.svg?style=flat-square)](https://travis-ci.org/ptavares/ansible-role-manage-system)
[![Ansible Role](https://img.shields.io/ansible/role/27842.svg)](https://galaxy.ansible.com/ptavares/ansible-role-manage-system)
[![Ansible Role](https://img.shields.io/ansible/quality/27842.svg)](https://galaxy.ansible.com/ptavares/ansible-role-packer)
[![Ansible Role](https://img.shields.io/ansible/role/d/27842.svg)](https://galaxy.ansible.com/ptavares/ansible-role-packer)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/ptavares/ansible-role-manage-system/blob/master/LICENSE)

ansible-role-mange-system
=========

Ansible role for managing system system (update - install/remove packages - clean)

Requirements
------------

Only tested with ansible 2.5 min version

Role Variables
--------------
Available variables are listed below, along with default values (see [defaults/main.yml](https://github.com/ptavares/ansible-role-manage-system/blob/master/defaults/main.yml)):

### System update

```yaml
# Wether or not call update-system task
system_update: false
# Whether or not only applies security updates
system_update_security_only: false
```
### Install/Remove packages

```yaml
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
system_deb_urls:
  - "https://prerelease.keybase.io/keybase_amd64.deb"

# --------------------
# Specific Centos/RHEL
# --------------------
system_rpm_urls:
  - "https://prerelease.keybase.io/keybase_amd64.rpm"
```
### Clean system

```yaml
# Wether or not call clean-system task
system_clean: true
```

Dependencies
------------

No dependencie

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ptavares.ansible_role_mange_system
```
Inside *`vars/main.yml`*:
- Copy content of [defaults/main.yml](https://github.com/ptavares/ansible-role-manage-system/blob/master/defaults/main.yml) in your playbook's vars file.
- Customize it as you like (filling role's variables) 

License
-------

MIT
