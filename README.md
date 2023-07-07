# nextcloud-ansible

An Ansible script used to deploy the Nextcloud instance.

This script can be used to deploy a number of Nextcloud instances on different machines with different domains.


## Prerequisites

You will need the following:

**1-** Linux machines with Python installed.

**2-** Docker daemon present and running on all target machines.

**3-** Ansible installed at least version 2.

**4-** *crypto* module already present to use openssl functionalities in Ansible.
If It's not installed, install it by:
```
ansible-galaxy collection install community.crypto
```

## Directory Structure

**docker-compose**: Contains files *docker-compose.yaml* as main docker compose file and *network.yaml* as network configurations.

**nginx**: Contains configuration and certificate files for *Nginx* container.

**inventory**: Ansible inventory file.

**nextcloud-pre.yaml**: Ansible playbook to deploy Nextcloud before setting up initialization via web interface.

**nextcloud-post.yaml**: Ansible playbook to deploy Nextcloud after setting up initialization via web interface.

**vars.yaml**: Variables used by playbooks that should be changed based on your needs.


## How to use it

Change the *vars.yaml* variables to suit your needs.

Add your hosts to *inventory* file or use your own inventory file.

There are two Ansible playbooks: **nextcloud-pre.yaml** & **nextcloud-post.yaml**.

**nextcloud-pre.yaml** is the scripts needed to run the Nextcloud on machines.
**nextcloud-post.yaml** is the scripts to finish deploying Nextcloud after first initialization by the web interface.

Run the script:
```
ansible-playbook -i inventory nextcloud-pre.yaml
```
After finishing setting up Nextcloud by Web UI, run the second playbook:
```
ansible-playbook -i inventory nextcloud-post.yaml
```
