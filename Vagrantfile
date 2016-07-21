# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.require_version ">= 1.7.0"
VAGRANT_API_VERSION = "2"

Vagrant.configure(VAGRANT_API_VERSION) do |config|
  config.vm.box = "debian/contrib-jessie64"
  config.vm.box_check_update = false

  # Forwarded port mapping (Host - to - Guest) 
  # Web Server Port
  config.vm.network "forwarded_port", guest: 80, host: 8080
  # Angular Ports
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 3001, host: 3001
  
  # Private network, using a specific static IP
  config.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)", ip: "192.168.1.192"

  # Provider-specific configuration
  # VirtualBox
  config.vm.define "ivy" do |ivy|
     ivy.vm.hostname = "Ivy.vm"
  end
  
  config.vm.provider "virtualbox" do |vb|
      vb.name = "Ivy"
      vb.memory = "1024"
      vb.cpus = 2
  end
  
  # Provisioning, allows Vagrant tool to install additional software
  config.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "master.yml"
  end
end
