ceph
====

Ansible role to configure and dump configuration of ceph client.

Requirements
------------

* [ansible.builtin](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html)
* [ansible.posix](https://docs.ansible.com/ansible/latest/collections/ansible/posix/index.html)
* [community.general](https://docs.ansible.com/ansible/latest/collections/community/general/)

Role Variables
--------------

* defaults

  * `main.yaml`

    ```yaml
    ceph_pkgs: []  # ceph-common package name
    ceph_groups: []  # local system group for ceph client account
    ceph_accounts:  []  # local system user for ceph client account
    ```

* vars

  ```yaml
  ceph_config_file: {}  # ceph client config path and attributes
  ceph_keyring: {}  # ceph keyring path and attributes
  ```

Dependencies
------------

* [software](https://github.com/mario-slowinski/software)
* [disk](https://github.com/mario-slowinski/disk)

Tags
----

* ceph.config
* ceph.keyring
* ceph.zabbix
* ceph.mount
* ceph.dump
  * ceph.dump.config
  * ceph.dump.pool
  * ceph.dump.osd
* ceph.metadata
  * ceph.metadata.mon
  * ceph.metadata.osd
  * ceph.metadata.mds
  * ceph.metadata.mgr

Examples
--------

* `requirements.yaml`

  ```yaml
  - name: ceph
    src: https://github.com/mario-slowinski/ceph
  ```

* `playbook.yaml`

  ```yaml
  - hosts: servers
    gather_facts: true
    roles:
      - role: ceph
  ```

License
-------

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html)

Author Information
------------------

[mario.slowinski@gmail.com](mailto:mario.slowinski@gmail.com)
