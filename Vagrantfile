# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "debian/jessie64"

    config.ssh.insert_key = false
  
    #install ansible in os
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get upgrade -y
      sudo apt-get install -y python-setuptools
      sudo easy_install pip
      sudo pip install ansible
    SHELL
  
    config.vm.provision "ansible_local" do |ansible|
      ansible.galaxy_role_file = "./provision/requirements.yml"
      ansible.playbook = "./provision/playbook.yml"
    end

end