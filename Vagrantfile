# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
VIRTUALBOX = "virtualbox"
VMWARE = "vmware_desktop"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "kalilinux/rolling"
  config.vm.box_version = "2021.2.0"
  config.vm.network :private_network, ip: "192.168.66.66"
  config.vm.hostname = "attacker"
  config.ssh.insert_key = false

  config.vm.provider VIRTUALBOX do |v|
    v.memory = 4096
    v.cpus = 4

#   config.vm.provider VMWARE do |v|
#     v.vmx["memsize"] = "4096"
#     v.vmx["numvcpus"] = "4"
  end

  # Ansible provisioner.
#   config.vm.provision :ansible do |ansible|
#     ansible.playbook = "site.yml"
#   end
end
