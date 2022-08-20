# Multinode Devstack deploying tool

For now, very simple and non-elegant. Many things are hardcoded. It supports 
two nodes of Devstack to play with instance migration, etc.

* Queens on Xenial, Python 2.7
* Rocky on Bionic, Python 3.6

Manual: https://docs.openstack.org/devstack/queens/guides/multinode-lab.html

## Requirements:
* 24GB RAM
* 10GB disk space

* virt-lightning
* ansible 2.9

* Fast connection to download tons of dependencies

## How to run
```
$ vl up
$ vl ansible_inventory > inventory
$ ansible-playbook -i inventory playbook.yaml
```

## TODOs
* Get rid of hardcoded IPs and so on
* Enable passwordless login to stack@...