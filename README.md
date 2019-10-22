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

|Key|Description|
|---|---|
|k8s_docker_repo|Docker repository url|
|k8s_docker_key|Docker repository key|
|k8s_docker_edition|Docker edition: ce, ee|
|k8s_docker_package|Docker package name<br> Default: docker-[k8s_docker_edition]|
|k8s_docker_packages|Docker packages to install<br> Default: [k8s_docker_package], [k8s_docker_package]-cli, containerd.io|
|k8s_kubernetes_repo|Kubernetes repository url|
|k8s_kubernetes_repo_key|Kubernetes repository key|
|k8s_kubernetes_packages|Kubernetes packages to install<br> Default: kubelet, kubeadm, kubectl|
|k8s_copy_auth_key|Copy local SSH key to remote|
|k8s_copy_auth_key_path|Local SSH key path<br> Default: ~/.ssh/id_rsa.pub|
|k8s_update_iptable_bridge_rules|Update iptables rules for receiving bridged IPv4 and IPv6 network traffic on the nodes|
|k8s_update_selinux|Disable SELinux|
|k8s_pod_network_cidr|Pod network<br> Default: 192.168.0.0/16 (Calico)|
|k8s_pod_network_driver_config|Pod network driver config<br> Default (Calico): https://docs.projectcalico.org/v3.8/manifests/calico.yaml|
|k8s_master_node_ip|Master node IP|
|k8s_node_name|Node hostname<br> Default: k8s.local|
|k8s_node_role|Node role: base, main-master, backup-master, worker|
|k8s_extras_install_helm|Install Helm|

Example Playbook
----------------

    ---
    - hosts: master
      become: true
      vars:
        - k8s_node_role: master
      roles:
        - antongorkovenko.k8s

License
-------

BSD

Author Information
------------------

[Anton Gorkovenko](https://github.com/antongorkovenko)
