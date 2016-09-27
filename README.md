# Vagrant Master Node 
This project uses Vagrant tool to build a local dev environment of the master node, which is also the monitoring node of Desmotes. So in master node, Desmotes project will install and run several tool packages using [Ansible](https://www.ansible.com/)

Desmotes Project chooses Vagrant to setup experimental environment for the master node. More extensible Desmotes Project uses: 
* Ubuntu 14.04 (LTS) / TrustyTahr distro
* Ansible / Provisioning mechanism

# Virtual Machine Creation 
Desmotes local dev environment uses Virtual Box as VM provider.

## Run Desmotes Vagrantfile

Go to the Desmotes' Vagrant location
 
> cd Desmotes/VagrantMasterNode/

> vagrant up

If you want to change something on provision phase after the VM's creation, you have to run the following command in the Desmotes' Vagrant location

> cd Desmotes/VagrantMasterNode/

> vagrant provision

Based on lifecycle of VM. More information can be found here [https://www.vagrantup.com/docs/provisioning/basic_usage.html]


# Desmotes Environment

## MariaDB

Desmotes service use following MariaDB configuration, which can be found in Wiki [here](https://github.com/Desmotes/VagrantMasterNode/wiki/MariaDB)


