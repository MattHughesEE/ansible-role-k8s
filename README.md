# Ansible Role: Kubernetes

[![Build Status](https://travis-ci.com/antongorkovenko/ansible-role-k8s.svg?branch=master)](https://travis-ci.com/antongorkovenko/ansible-role-k8s)

Ansible role to install Kubernetes

Supported platforms
-------------------

* Amazon linux 2
* CentOS 7
* RHEL 7
* Debian 9+
* Ubuntu 16+

Role Variables
--------------

See defaults/main.yml

Example Playbook
----------------

    ---
    - hosts: master
      become: true
      vars:
        - node_role: master
      roles:
        - antongorkovenko.k8s

License
-------

BSD

Author Information
------------------

[Anton Gorkovenko](https://github.com/antongorkovenko)
