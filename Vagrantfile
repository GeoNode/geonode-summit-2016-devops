# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "bento/ubuntu-16.04"

  config.vm.network "forwarded_port", guest: 4000, host: 8000

  config.vm.synced_folder "~/workspaces/public/geonode-summit-2016.git", "/home/vagrant/geonode-summit-2016.git"

  config.vm.provider "virtualbox" do |vb|\
      vb.gui = true
      vb.cpus = 2
      vb.memory = 4096
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/ubuntu_geonode_summit_2016.yml"
    ansible.host_key_checking = false
    ansible.verbose = "v"
    ansible.raw_arguments = []
  end

end
