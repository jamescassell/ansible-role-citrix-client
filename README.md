citrix-client
=============

Install Citrix Client application.  Receiver or Workspace.

Requirements
------------

- The ICAClient package must be available for installation, or already
  installed.

- If the package is already installed, `update-ca-trust` should be run
  afterwards (or at least sometime after the ICAClient rpm was built) for this
  role to install system CA certificates into the Citrix Client trust store.

Role Variables
--------------

```
citrix_client_packages: [ICAClient]  # the path to the .rpm file
citrix_client_trust_args: ""  # extra args to pass to 'trust extract'
```

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
      - role: citrix-client
        # specify custom package mirror location
        citrix_client_packages:
        - https://mirror.example.com/downloads.citrix.com/16914/ICAClient-rhel-19.12.0.19-0.x86_64.rpm
        # trust only locally-trusted certs, not default CAs
        citrix_client_trust_args: --filter pkcs11:token=System%20Trust

License
-------

Apache-2.0 or MIT or BSD-3-Clause

Author Information
------------------

[James Cassell](https://github.com/jamescassell)
