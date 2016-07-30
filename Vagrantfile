# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.require_version ">= 1.7.0"
VAGRANT_API_VERSION = "2"

Vagrant.configure(VAGRANT_API_VERSION) do |config|
  # Ubuntu 14.04 distro 
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false

  # Provider-specific configuration
  # VirtualBox 
  # Guest Machine - Desmotes Controller
  # ivy (DC character - google it :P)
  config.vm.define "ivy" do |ivy|
     ivy.vm.hostname = "Ivy.vm"
     # Forwarded port mapping (Host - to - Guest) 
     # Web Server Port
     ivy.vm.network "forwarded_port", guest: 80, host: 8080
     # Angular Ports for GUI
     ivy.vm.network "forwarded_port", guest: 3000, host: 3000
     ivy.vm.network "forwarded_port", guest: 3001, host: 3001
     # Private network with static IP (192.168.1.192)
     ivy.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)", ip: "192.168.1.192"
  end
  
  config.vm.provider "virtualbox" do |vb|
      vb.name = "Ivy"
      vb.memory = "1024"
      vb.cpus = 2
  end
 
  # Synchronized folder. It is obligatory for ansible local.
  config.vm.synced_folder ".", "/vagrant"
 
  # Provisioning, allows Vagrant tool to install additional software
  config.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "ProvisioningMasterNode/master_node.yml"
      ansible.inventory_path = "ProvisioningMasterNode/master_local"
      ansible.vault_password_file = "ProvisioningMasterNode/.vault_pass"
      ansible.install = true
      ansible.verbose = "v"
      ansible.limit = "all"
      ansible.version = "latest"
  end
end
