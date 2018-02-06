Ansible-MotionEye
=========
[![Build Status](https://travis-ci.org/sirmaxim/ansible-role-motioneye.svg?branch=master)](https://travis-ci.org/sirmaxim/ansible-role-motioneye)

This role will deploy [motioneye](https://github.com/ccrisan/motioneye/) on a server and has been tested on Ubuntu 16.04.

Requirements
------------

You will need at least a `v4l-utils` compatible camera or IP camera to provide a feed to monitor. This uses `Python 2.7` and will require some changes if your target host defaults to python3.

Role Variables
--------------

```yaml
motioneye_user: motioneye # The user the service will run as.
motioneye_home: /home/motioneye # user $HOME for config/data storage.
motioneye_port: 8765 # Port the web interface will listen on
motioneye_listen: 0.0.0.0 # IP address to listen on.
```

Dependencies
------------

No other roles required.

Example Playbook
----------------

```yaml
---
- hosts: 10.0.0.1
  gather_facts: true
  become: true

  pre_tasks:


  roles:
    - { role: base , tags: ["base"] }
    - motioneye



  handlers:
    - include: common/handlers/main.yml

```


License
-------

MIT

Author Information
------------------

This role was written in 2017 by Matt Whitehead.
