# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  # config.vm.box = "chef/centos-6.5"

  config.vm.network "forwarded_port", guest: 80, host: 9999
  config.vm.network "private_network", ip: "192.168.3.11"

  # config.vm.network "public_network"
  config.vm.synced_folder "./data", "/data"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  config.vm.provision 'ansible' do |ansible|
    ansible.playbook = 'provision/playbook.yml'
    # ansible.verbose = 'vvv'
  end
end
