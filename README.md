# sfr-preinstall

- configure timezone

- configure nameservers

- configure apt proxy

- configure Astra Linux repositories

- install essential packages

- configure root .bachrc from template


For first, define the environment in inventory.ini like this:

```
[all:vars]
env=prod
ansible_user=sysman
ansible_ssh_private_key_file=~/.ssh/id_rsa
```

It used in environment variable access playbooks. For example:

```
---
# vim: syntax=yaml tabstop=2 shiftwidth=2
- hosts: all
  vars_files:
    - group_vars/{{ env }}.yml
  roles:
    - { role: preinstall, tags: preinstall }
...
```
