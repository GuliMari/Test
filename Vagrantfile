# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.define "ubuntu" do |ubuntu|
      ubuntu.vm.box = "ubuntu/bionic64" # Ubuntu 18.04 box
      ubuntu.vm.network "private_network", type: "dhcp"
      ubuntu.vm.network "forwarded_port", guest: 8080, host: 8082
      ubuntu.vm.provider "virtualbox" do |vb|
        vb.memory = "1024" # Set the desired RAM size
      end
    end


    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "docker.yml"
      end
  end
  