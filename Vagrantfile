# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
VIRTUALBOX = "virtualbox"
VMWARE = "vmware_desktop"
VM_NAME = "attacker"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "kalilinux/rolling"
  config.vm.box_version = "2021.2.0"
  config.vm.network :private_network, type: "dhcp"
  config.vm.hostname = VM_NAME
  config.ssh.insert_key = false

  config.vm.provider VIRTUALBOX do |v|
    v.name = VM_NAME
    v.memory = 2048
    v.cpus = 2

    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--vram", "256"]
      vb.customize ["modifyvm", :id, "--accelerate3d", "on"]
    end

    #   config.vm.provider VMWARE do |v|
    #     v.vmx["memsize"] = "4096"
    #     v.vmx["numvcpus"] = "4"
  end

  # Ansible provisioner.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "site.yml"
  end
end
