# Vagrant

## Prerequisites

* [Virtualbox](https://www.virtualbox.org/wiki/Downloads)

* SSH-keys in local agent:

    ssh-add -L
    ssh-add ~/.ssh/id_rsa

* To start up ssh-agent

    ssh-agent /bin/bash


## Packages

* Base
* Apache
* MySQL
* Java
* Rbenv


## Provision

    vagrant destroy && vagrant up

## Access

    ssh deploy@localhost -p 2222


## Google Cloud

### Install GCUTIL

    curl https://sdk.cloud.google.com | bash

### Access target server

    ssh -o UserKnownHostsFile=/dev/null -o CheckHostIP=no -o StrictHostKeyChecking=no -i /Users/<user>/.ssh/google_compute_engine -A -p 22 <user>@<ip>

### Deploy

    ansible-playbook provisioning/playbook.yml -i provisioning/hosts.google -u <user> --private-key=/Users/<user>/.ssh/google_compute_engine

