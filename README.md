citrix-client
=============

Install Citrix Client application.  Receiver or Workspace.

Requirements
------------

- The ICAClient package must be available for installation, or already
  installed.

- If the package is already installed, `update-ca-trust` should be run
  afterwards for this role to install system CA certificates into the Citrix
  Client trust store.

Role Variables
--------------

```
citrix_client_packages: [ICAClient]  # the path to the .rpm file
```

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
      - role: citrix-client
        citrix_client_packages:
        - https://mirror.example.com/downloads.citrix.com/16914/ICAClient-rhel-19.12.0.19-0.x86_64.rpm

License
-------

Apache-2.0 or MIT or BSD-3-Clause

Author Information
------------------

[James Cassell](https://github.com/jamescassell)
