# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  config.vm.network "private_network", ip: "192.168.56.101"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
  end

  config.vm.provision :ansible do |ansible|
    ansible.galaxy_role_file = "requirements.yml"
    ansible.playbook = "playbook.yml"
    ansible.raw_ssh_args = ["-o ForwardAgent=yes"]
  end
end
