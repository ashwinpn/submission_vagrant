# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "ubuntu/bionic64"

  
   config.vm.provider "virtualbox" do |vb|
     # Display the VirtualBox GUI when booting the machine
     vb.gui = false

     # Customize the amount of memory on the VM:
     vb.memory = "2048"
   end
 
   config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get -y upgrade apt-get update
     sudo apt-get -y install python3.8 python3.8-dev python3.8-distutils python3.8-venv
     sudo apt-get -y install git-all python-dev 
     curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
     python3.8 get-pip.py
     pip install future nose mock coverage numpy flake8  
     pip --no-cache-dir install torch torchvision
   SHELL
end
