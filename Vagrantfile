# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.network "forwarded_port", guest: 80, host: 8070
  config.vm.network "private_network", ip:"192.168.50.4"
  config.ssh.insert_key=false
  config.vm.synced_folder ".", "/vagrant", disabled:true

  config.vm.provider :virtualbox do |v|
    v.memory = 1024
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
