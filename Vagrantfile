# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANT_API_VER = "2"

Vagrant.configure(VAGRANT_API_VER) do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", type: "nfs"

  config.vm.provider :virtualbox do |vb|
    vb.name = "jenkins"
    vb.memory = 1024
    vb.cpus = 2
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.hostname = "jenkins"
  config.vm.network :private_network, ip: "192.168.1.200"

  # Set the name of the VM
  config.vm.define :jenkins do |jenkins|
  end

  # Ansible provisioner
  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "provisioning/playbook.yml"
    ansible.inventory_path = "provisioning/inventory"
    ansible.become = true
  end

end
