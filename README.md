# Description

This playbook's aim is to deploy and base configure a taskd server.
Currently it's working only with Ubuntu Server 16.04 (LTS).

This playbook doesn't handle the task (client) installation. Refer to http://taskwarrior.org/download/#setup for help.

# Usage

## Install python 2.7

Ubuntu 16.04 switched completely to python3. In the default installation there is no python2. Ansible works currently only with python2 so you need to have python2 installed before running the playbook.

```
ansible-playbook -i taskd-server.domain, install_python.yml
```

## Install and configure taskd

Adjust variables, if needed, in `vars/main.yml`

```
ansible-playbook -i taskd-server.domain, main.yml
```

## Add user (client)

```
ansible-playbook -i taskd-server.domain, add_user.yml -e 'taskd_org=Public taskd_client=testuser'
```

# Links

* [http://taskwarrior.org/](Taskwarrior)
