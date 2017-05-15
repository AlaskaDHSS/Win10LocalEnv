# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # https://docs.vagrantup.com.

  config.vm.guest = :windows
  config.vm.communicator = :winrm
  config.winrm.username = "vagrant"
  config.winrm.password = "vagrant"
  config.vm.box = "packer/windows_10_virtualbox.box"

  config.vm.network "private_network", ip: "10.10.10.10"
  
  # Simplify shared folders.  ".." is /dev on my host.
  #  Vagrant automatically shares "." with /vagrant.
  config.vm.synced_folder "..", '/dev'

  config.vm.provider :virtualbox do |vb|
    vb.gui = false 
  end

 end