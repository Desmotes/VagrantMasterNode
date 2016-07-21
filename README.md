# Vagrant Master Node 
This project uses Vagrant tool to build a development environment of the master node, which is also the monitoring node of Desmotes.

Desmotes Project chooses Vagrant to setup experimental environment for the master node. More extensible Desmotes Project uses: 
* Debian / jessies distro
* Ansible / Provisioning mechanism 

# Virtual Machine Creation 
Desmotes development environment uses Virtual Box as VM provider.

Creating the Vagrantfile

> vagrant init debian/contrib-jessie64; vagrant up --provider virtualbox

Running Provisioners

Provisioners are run in three cases: The initial vagrant up, vagrant provision, and vagrant reload --provision

> vagrant up 

> vagrant provision

> vagrant reload --provision

Based on lifecycle of VM. More information can be found here [https://www.vagrantup.com/docs/provisioning/basic_usage.html]

