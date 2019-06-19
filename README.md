# Amtega oracle_jdbc_connector role

This is an [Ansible](http://www.ansible.com) role to deploy Oracle JDBC connector.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

The role setups the following facts:

- oracle_jdbc_connector_jar_path: full path to the deployed jar with the connector.

## Example Playbook

This is an example playbook:

``` yaml
---
- name: msyql_jdbc_connector role sample
  hosts: localhost
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

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

To run test you need to provide a registered user/password form the Oracle web site to fill role's `oracle_jdbc_connector_user` and `oracle_jdbc_connector_password` variables. One way to provide this information is calling the testing playbook passing an additional vault inventory plus the default one provided for testing, as it's show in this example:

```shell
$ cd amtega.oracle_jdbc_connector/tests
$ ansible-playbook main.yml -i inventory -i ~/mycustominventory.yml --vault-id myvault@prompt
```

## License

Copyright (C) 2019 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Juan Antonio Valiño García.
