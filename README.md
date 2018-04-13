Percona Host
============
- Installs Percona XtraDB Cluster (or Server) 5.7 on CentOS 7.4
- Firewalld rules configured based on selected install (cluster or server)

**NOTE**: SELinux needs to be in permissive mode or disabled if using Percona XtraDB clustering; see offical [install guide](https://www.percona.com/doc/percona-xtradb-cluster/LATEST/install/yum.html)


Requirements
------------
None.


Role Variables
--------------
- config_cluster
- config_tls
- cert_src_path
- tls_ca_cert
- tls_ca_key
- wsrep_cluster_address
- wsrep_cluster_name
- wsrep_sst_user
- wsrep_sst_password
- config_fw
- fw_zone_name
- package_cluster_name
- package_name
- repo_url


Dependencies
------------
None.


Example Playbook
----------------

```
- hosts: all
  vars_prompt:
    - name: "config_cluster"
      prompt: "> Install Percona XtraDB Cluster?"
      private: no
      default: true

    - name: "config_fw"
      prompt: "> Configure firewall rules?"
      private: no
      default: true

  tasks:
    - name: Install Percona
      import_role: 
        name: percona-host
```


License
-------
BSD


Author Information
------------------
[EasyPath IT Solutions Inc.](https://www.easypath.ca)

