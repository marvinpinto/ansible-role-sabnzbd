sabnzbd
=======

[![Build Status](https://img.shields.io/travis/marvinpinto/ansible-role-sabnzbd/master.svg?style=flat-square)](https://travis-ci.org/marvinpinto/ansible-role-sabnzbd)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-sabnzbd-blue.svg?style=flat-square)](https://galaxy.ansible.com/marvinpinto/sabnzbd)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.txt)

Ansible Galaxy role to install and manage [sabnzbd](http://sabnzbd.org).


Requirements
------------

This role has been tested on Ubuntu 14.04 and will likely only work on an
Ubuntu-like system.


Role Variables
--------------

``` yaml
# Application config
sabnzbd_app_directory: '/opt/sabnzbd'

# Daemon config
sabnzbd_daemon_user: 'sabdownloader'
sabnzbd_daemon_host: '127.0.0.1'
sabnzbd_daemon_port: '8080'
sabnzbd_daemon_extra_args: ''
sabnzbd_daemon_config_file: "{{ sabnzbd_app_directory }}/config/sabnzbd.ini"

# nzbtomedia config
sabnzbd_nzbtomedia_directory: '/opt/nzbtomedia'
sabnzbd_nzbtomedia_autoprocessmedia_cfg: |
  # nzbToMedia Configuration
  # For more information, visit https://github.com/clinton-hall/nzbToMedia/wiki

  [General]
      # Enable/Disable update notifications

  ...
  (the rest of the contents of your autoProcessMedia.cfg here)
  ...
```


Examples
--------

Install this module from Ansible Galaxy into the './roles' directory:
```bash
ansible-galaxy install marvinpinto.sabnzbd -p ./roles
```

Use it in a playbook as follows:
```yaml
- hosts: '127.0.0.1'
  roles:
    - role: 'marvinpinto.sabnzbd'
      become: true
```


Local Testing
-------------
Use the supplied `Vagrantfile` for local development and testing (hint: `vagrant up --provision`)
