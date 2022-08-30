# Ansible role for creating a lxd container
==========================================

**summary**

This role is for creating a lxd container 
Look in the tasks directory for each configuration.
All configurations are held atomically via their own files.

***Optional Features***
None at the moment.


## Necessary preparations
Role Cloudinit

## Variables that have to be defined

| variable | description | mandantory |
| -------- | ----------- | ---------- |
| cloudinit_rendering | Choose the cloudinit (role) redering **Predefined**: ```{{ cloudinit_rendering: "container" }}```. Overwrite if necessary.| False |
| alias | Ubuntu Version **Predefined**: ```{{ alias: "22.04" }}```. Overwrite if necessary.| False |
| profiles | Select the Profile to use by container **Predefined**: ```{{ profiles: "default" }}```. Overwrite if necessary.| False |
| host | Host on which the container will be created. | True |

# example playbook
```
---
- hosts: 
    - example.com
  become: True
  vars:
    gitlab_ce_hostname: example.com
  vars_files:
    - group_vars/vault.yml
  tasks:
  roles:
    - lxd-container
```