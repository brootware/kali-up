# kali-up
# -*- mode: ruby -*-
# vi: set ft=ruby :

############################################################
# VM settings variables - Can be reviewed and customized
############################################################

# VAGRANTFILE_API_VERSION: to choose which API to use. Recommended to use 2.
VAGRANTFILE_API_VERSION = "2"

# VARIABLES to use either virtualbox or vmware as provider
VIRTUALBOX = "virtualbox"
# VMWARE = "vmware_fusion"

# VM_PATH:  the name or full url of the base VM to use
VM_PATH = "kalilinux/rolling"

# VM_UPDATE: set to true to check for base VM updates
VM_UPDATE = true

# VM_Name: can be changed here
VM_NAME = "attacker"

# VM_CPUS: specify the number of CPU cores to allocate to the VM
# VM_CPUS = "4"
VM_CPUS = "2"

# VM_MEMORY: specify the amount of memory to allocate to the VM
#VM_MEMORY = "8192"
VM_MEMORY = "4096"
#VM_MEMORY = "2048"

############################################################
# THE COMPONENTS BELOW SHOULD NOT BE ALTERED
############################################################

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = VM_PATH
  config.vm.network :private_network, type: "dhcp"
  config.vm.hostname = VM_NAME
  config.ssh.insert_key = false

  config.vm.provider VIRTUALBOX do |vb|
    vb.name = VM_NAME
    vb.cpus = VM_CPUS
    vb.memory = VM_MEMORY
    vb.customize ["modifyvm", :id, "--vram", "256"]
    vb.customize ["modifyvm", :id, "--accelerate3d", "on"]
  end

  # VMWARE FUSION CONFIG is currently in development
  # config.vm.provider VMWARE do |vw|
  #   vw.vmx["numvcpus"] = VM_CPUS
  #   vw.vmx["memsize"] = VM_MEMORY
  # end

  # Ansible provisioner.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "site.yml"
  end
end
