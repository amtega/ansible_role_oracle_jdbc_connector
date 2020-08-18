# Amtega oracle_jdbc_connector role

This is an [Ansible](http://www.ansible.com) role to deploy Oracle JDBC connector.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

The role setups the following facts:

- `oracle_jdbc_connector_[component]_jar_path`: full path to the deployed commponent jar with the connector.

## Example Playbook

This is an example playbook:

``` yaml
---
- hosts: localhost
  roles:  
    - amtega.oracle_jdbc_connector
  vars:    
    oracle_jdbc_connector_state: present
    oracle_jdbc_connector_version: 12.2.0.1
    oracle_jdbc_connector_dir: /root
    oracle_jdbc_connector_download_dest: /root     
    oracle_jdbc_connector_user: acme
    oracle_jdbc_connector_password: acme
```

## Testing

Tests are based on [molecule with docker containers](https://molecule.readthedocs.io/en/latest/installation.html).

To run test you need to provide a registered user/password from the Oracle web site to fill role's `oracle_jdbc_connector_user` and `oracle_jdbc_connector_password` variables. You can do it calling the tests with the following environment variables:

- `ANSIBLE_INVENTORY`: path to an inventory providing the variables required by the role
- `ANSIBLE_VAULT_PASSWORD_FILE`: path to the file containing the vault password required for the previous inventory (optional)

```shell
cd amtega.oracle_jdbc_connector

ANSIBLE_INVENTORY=~/myinventory ANSIBLE_VAULT_PASSWORD_FILE=~/myvaultpassword molecule test
```

## License

Copyright (C) 2020 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Juan Antonio Valiño García.
