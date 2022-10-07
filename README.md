# Simple Hetzner API Ansible roles and scripts

## Overview

My first attempt using ansible to manage, install and setup ubuntu 22.04 on a rented Cloud Server from http://hetzner.de using their Ansible Module (API).

## Preparation

### Brew
```
brew install git
brew install ansible
ansible --version
brew install hcloud
```

### Python 
```
sudo easy_install pip
pip install ansible
ansbile --version
pip install hcloud
```
### HCLOUD_TOKEN

At Hetzner, an API token must be created for the secure connection. This must then be linked and used with the following
command and deploy it. Is only valid as long as the terminal session.
```
export HCLOUD_TOKEN="The API-Key"
```

## Configuration

### Checking the connection to Hetzner
View a list of all available resources
```
ansible-inventory -i inventories/hcloud/demo.hcloud.yml --list     
```

### Set up the Hetzner environment with server, firewall and other settings
```
ansible-playbook playbooks/create.yml
```