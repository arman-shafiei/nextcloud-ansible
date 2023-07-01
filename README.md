# nextcloud-ansible

An Ansible script used to deploy Nextcloud instance.

This script can be used to deploy a number of Nextcloud instances on different machines with different domains.

## Prerequisites
You will be needing the following:

**1-** Linux machines with Python installed.

**2-** Docker daemon present and running on all target machines.

**3-** Ansible installed at least version 2.

**4-** Install *crypto* module to add openssl functionalities to Ansible:
```
ansible-galaxy collection install community.crypto
```
