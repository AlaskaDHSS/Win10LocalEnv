# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # https://docs.vagrantup.com.

  config.vm.guest = :windows
  config.vm.communicator = :winrm
  config.winrm.username = "vagrant"
  config.winrm.password = "vagrant"
  config.vm.box = "packer/windows_10_virtualbox"

  config.vm.network "private_network", ip: "10.10.10.10"

  config.vm.provider :virtualbox do |vb|
    vb.gui = false 
  end

 end