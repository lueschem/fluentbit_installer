fluentbit_installer
===================

Ansible role that installs fluentbit on a Debian IoT node.

Requirements
------------

The role can be applied to a basic Debian installation. Data can be written to an InfluxDB cloud
instance.

Role Variables
--------------

To enable output to an InfluxDB database all of the following variables need to be defined.

- influxdb_server: The InfluxDB server URL.
- influxdb_bucket: The InfluxDB bucket.
- influxdb_http_token: The InfluxDB token.
- influxdb_org: The InfluxDB organization.


Dependencies
------------

The role is not based upon any other roles.


Example Playbook
----------------

A basic playbook that makes use of this role could look like this:

```
---
- hosts: all

  vars:
    influxdb_server: some-server
    influxdb_bucket: some-bucket
    influxdb_http_token: some-token
    influxdb_org: some-org

  roles:
    - role: fluentbit_installer
      become: true
```

Testing
-------

The following command can be used to apply the role to the local machine.

```
sudo ansible-playbook --connection=local -i fluentbit_installer/tests/inventory fluentbit_installer/tests/test.yml --extra-vars "influxdb_server=some-server influxdb_bucket=some-bucket influxdb_http_token=some-token influxdb_org=some-org"
```

License
-------

MIT

Author Information
------------------

https://www.get-edi.io
