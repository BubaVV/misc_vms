# Collection of templates to spin up VMs for various jobs

## Devstack

Typical Devstack requires 8 Gb of RAM and 10 Gb of disk space. Separate 
folders for Devstack branches and specific configs, like enabled OVS. 

Playbook sets up everything in VM, clones proper branch of Devstack and do 
`unstack.sh` and `stack.sh` commands. Playbook run is idempotent, so 
recurring run just repeats unstack and stack scripts. It allows to repair some 
minor problems without VM re-deploy.

## Multinode Devstack

Detailed manual in folder. Workflow is the same like regular Devstack.

## Various VMs for misc purposes

* xenial4queens

    VM with Ubuntu Xenial and some preinstalled dependencies to run tests 
    for Openstack Queens

## How to run

Tool relies on 
[virt-lightning](https://github.com/virt-lightning/virt-lightning) Python 
package and Ansible 2.9. Virt-lightning uses libvirt as backend.

Commands to deploy an environment:
```
$ vl up # Prepare and pre-configure a VM
$ vl ansible_inventory > inventory # generate Ansible inventory
$ ansible-playbook -i inventory playbook.yaml # run Ansible Playbook and setup everything
```