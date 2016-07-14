Ansible MySecureShell role [![Build Status](https://travis-ci.org/mysecureshell/ansible-mysecureshell.svg?branch=master)](https://travis-ci.org/deimosfr/ansible-elasticsearch)
=====

This role installs and configures [MySecureShell](https://github.com/mysecureshell/mysecureshell) on a server.

Requirements
------------

This role requires Ansible 1.6 or higher and platform requirements are listed
in the metadata file.

Role Variables
--------------

The variables that can be passed to this role and a brief description about
them are as follows.

```yaml
---

# Set it to false and uncomment the desired lines below if you don't want to
# install the version provided by your distribution
mysecureshell_use_distribution_repo: true

# Debian
#mysecureshell_apt_repo: "deb http://mysecureshell.free.fr/repository/index.php/debian/7.1 testing main"
#mysecureshell_apt_repo: "deb http://mysecureshell.free.fr/repository/index.php/debian/6.0 testing main"

# Ubuntu
#mysecureshell_apt_repo: "deb http://mysecureshell.free.fr/repository/index.php/ubuntu/12.04 testing main"
#mysecureshell_apt_repo: "deb http://mysecureshell.free.fr/repository/index.php/ubuntu/10.10 testing main"

# RedHat/CentOS
#mysecureshell_yum_repo: "http://mysecureshell.free.fr/repository/index.php/centos/6.4/"
#mysecureshell_yum_repo: "http://mysecureshell.free.fr/repository/index.php/centos/5.5/"

# Fedora
#mysecureshell_yum_repo: "http://mysecureshell.free.fr/repository/index.php/fedora/19/"
#mysecureshell_yum_repo: "http://mysecureshell.free.fr/repository/index.php/fedora/17/"

mysecureshell_config:
  Default:
    Home: "/home/$USER"
    VirtualChroot: "true"
#  Group:
#    - name: "admins"
#      Download: "10M"
#    - name: "others"
#      Download: "1M"
#  User:
#    - name: "superuser"
#      VirtualChroot: "false"
#      Download: "100M"

# Update users list to MySecureShell shell
mysecureshell_users:

mysecureshell_manage_service: true
mysecureshell_binary_path: "/usr/bin/mysecureshell"
```

To know more about MySecureShell configuration, please refer to the [documentation](https://mysecureshell.readthedocs.io).

Examples
========

```yaml
# Roles
- name: MySecureShell Servers
  hosts: sftp
  user: root
  roles:
    - deimosfr.mysecureshell
```

Dependencies
------------

None

License
-------

GPL

Author Information
------------------

Pierre Mavro / deimosfr
