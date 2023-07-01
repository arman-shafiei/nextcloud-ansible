# nextcloud-ansible

An Ansible script used to deploy Nextcloud instance.

This script can be used to deploy a number of Nextcloud instances on different machines with different domains.

## Prerequisites
You will be needing the following:

**1-** Linux machines with Python installed.

**2-** Docker daemon present and running on all target machines.

**3-** Ansible installed at least version 2.

**4-** *crypto* module already present to use openssl functionalities in Ansible.
If It's not installed, install it by:
```
ansible-galaxy collection install community.crypto
```

## How to use it
Change the *vars.yaml* variables to suit your needs.

Add your hosts to *inventory* file or use your own inventory file.

There are two Ansible playbooks: **nextcloud-pre.yaml** & **nextcloud-post.yaml**.

**nextcloud-pre.yaml** is the scripts needed to run the Nextcloud on machines.
**nextcloud-post.yaml** is the scripts to finish deploying Nextcloud after first initialization by web interface.

Run the script:
```
ansible-playbook -i inventory nextcloud-pre.yaml
```
After finishing setting up Nextcloud by Web UI, run the second playbook:
```
ansible-playbook -i inventory nextcloud-post.yaml
```
