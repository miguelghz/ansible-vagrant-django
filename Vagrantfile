# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "geerlingguy/ubuntu1604"
  config.vm.network "forwarded_port", guest: 8000, host: 8000
  config.vm.network "public_network"
  
  config.ssh.forward_agent = true
  
  config.vm.synced_folder "./djangoproject", "/var/www/djangoproject"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/vagrant.yml"
  end
end

