# kali-up
# Credit - This vagrantfile is developed by referring to https://github.com/stevemcilwain/Disposable-Kali/blob/master/Vagrantfile
# -*- mode: ruby -*-
# vi: set ft=ruby :

############################################################
# VM settings variables - Can be reviewed and customized
############################################################

# VAGRANTFILE_API_VERSION: to choose which API to use. Recommended to use 2.
VAGRANTFILE_API_VERSION = "2"

# VARIABLES for virtualbox and vmware as provider
VIRTUALBOX = "virtualbox"
VMWARE = "vmware_fusion"

# Use VMWARE instead? Set below to true. DO NOTE IT'S STILL IN DEVELOPMENT.
USE_VMWARE = false

# VM_PATH:  the name or full url of the base VM to use
VM_PATH = "kalilinux/rolling"

# VM_UPDATE: set to true to check for base VM updates
VM_UPDATE = true

# VM_Name: can be changed here
VM_NAME = "attacker"

# VM_CPUS: specify the number of CPU cores to allocate to the VM
VM_CPUS = "4"
# VM_CPUS = "2"

# VM_MEMORY: specify the amount of memory to allocate to the VM
#VM_MEMORY = "8192"
VM_MEMORY = "4096"
#VM_MEMORY = "2048"

########################################################################################
# THE COMPONENTS BELOW SHOULD NOT BE ALTERED UNLESS YOU KNOW WHAT YOU'RE DOING
########################################################################################

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = VM_PATH
  config.vm.network :private_network, type: "dhcp"
  config.vm.hostname = VM_NAME
  config.vm.box_check_update = VM_UPDATE
  config.ssh.insert_key = false

  if USE_VMWARE == true
    # VMWARE FUSION CONFIG. Refer to vmxconfigref.txt for development and configuration changes.
    config.vm.provider VMWARE do |vw|
      vw.gui = true
      vw.allowlist_verified = true
      vw.vmx[".encoding"] = "UTF-8"
      vw.vmx["config.version"] = "8"
      vw.vmx["virtualHW.version"] = "8"
      vw.vmx["pciBridge0.present"] = "TRUE"
      vw.vmx["pciBridge4.present"] = "TRUE"
      vw.vmx["pciBridge4.virtualDev"] = "pcieRootPort"
      vw.vmx["pciBridge4.functions"] = "8"
      vw.vmx["pciBridge5.present"] = "TRUE"
      vw.vmx["pciBridge5.virtualDev"] = "pcieRootPort"
      vw.vmx["pciBridge5.functions"] = "8"
      vw.vmx["pciBridge6.present"] = "TRUE"
      vw.vmx["pciBridge6.virtualDev"] = "pcieRootPort"
      vw.vmx["pciBridge6.functions"] = "8"
      vw.vmx["pciBridge7.present"] = "TRUE"
      vw.vmx["pciBridge7.virtualDev"] = "pcieRootPort"
      vw.vmx["pciBridge7.functions"] = "8"
      vw.vmx["vmci0.present"] = "TRUE"
      vw.vmx["hpet0.present"] = "TRUE"
      vw.vmx["nvram"] = "Kali-Linux-2021.4a-vmware-amd64.nvram"
      vw.vmx["virtualHW.productCompatibility"] = "hosted"
      vw.vmx["powerType.powerOff"] = "soft"
      vw.vmx["powerType.powerOn"] = "soft"
      vw.vmx["powerType.suspend"] = "soft"
      vw.vmx["powerType.reset"] = "soft"
      vw.vmx["displayName"] = VM_NAME
      vw.vmx["usb.vbluetooth.startConnected"] = "TRUE"
      vw.vmx["guestOS"] = "debian10-64"
      vw.vmx["tools.syncTime"] = "TRUE"
      vw.vmx["sound.autoDetect"] = "TRUE"
      vw.vmx["sound.present"] = "TRUE"
      vw.vmx["numvcpus"] = VM_CPUS
      vw.vmx["cpuid.coresPerSocket"] = "2"
      vw.vmx["vcpu.hotadd"] = "TRUE"
      vw.vmx["memsize"] = VM_MEMORY
      vw.vmx["scsi0.virtualDev"] = "lsilogic"
      vw.vmx["scsi0.present"] = "TRUE"
      vw.vmx["scsi0:0.present"] = "TRUE"
      vw.vmx["ide1:0.deviceType"] = "cdrom-raw"
      vw.vmx["ide1:0.fileName"] = "auto detect"
      vw.vmx["ide1:0.present"] = "TRUE"
      vw.vmx["usb.present"] = "TRUE"
      vw.vmx["ehci.present"] = "TRUE"
      vw.vmx["ethernet0.connectionType"] = "nat"
      vw.vmx["ethernet0.addressType"] = "generated"
      vw.vmx["ethernet0.virtualDev"] = "e1000"
      vw.vmx["serial0.fileType"] = "thinprint"
      vw.vmx["serial0.fileName"] = "thinprint"
      vw.vmx["ethernet0.present"] = "TRUE"
      vw.vmx["scsi0:0.redo"] = ""
      vw.vmx["pciBridge0.pciSlotNumber"] = "17"
      vw.vmx["pciBridge4.pciSlotNumber"] = "21"
      vw.vmx["pciBridge5.pciSlotNumber"] = "22"
      vw.vmx["pciBridge6.pciSlotNumber"] = "23"
      vw.vmx["pciBridge7.pciSlotNumber"] = "24"
      vw.vmx["scsi0.pciSlotNumber"] = "16"
      vw.vmx["usb.pciSlotNumber"] = "32"
      vw.vmx["ethernet0.pcislotnumber"] = "160"
      vw.vmx["sound.pciSlotNumber"] = "34"
      vw.vmx["ehci.pciSlotNumber"] = "35"
      vw.vmx["svga.vramSize"] = "134217728"
      vw.vmx["vmotion.checkpointFBSize"] = "134217728"
      vw.vmx["ethernet0.generatedAddressOffset"] = "0"
      vw.vmx["vmci0.id"] = "-857322166"
      vw.vmx["monitor.phys_bits_used"] = "40"
      vw.vmx["usb:1.speed"] = "2"
      vw.vmx["usb:1.present"] = "TRUE"
      vw.vmx["usb:1.deviceType"] = "hub"
      vw.vmx["usb:1.port"] = "1"
      vw.vmx["usb:1.parent"] = "-1"
      vw.vmx["chipset.useAcpiBattery"] = "TRUE"
      vw.vmx["chipset.useApmBattery"] = "TRUE"
      vw.vmx["isolation.tools.hgfs.disable"] = "FALSE"
      vw.vmx["floppy0.present"] = "FALSE"
      vw.vmx["usb.generic.autoconnect"] = "FALSE"
      vw.vmx["usb.generic.allowHID"] = "TRUE"
      vw.vmx["guestInfo.detailed.data"] = "architecture='X86' bitness='64' distroName='Kali' distroVersion='2021.4' familyName='Linux' kernelVersion='5.14.0-kali4-amd64' prettyName='Kali GNU/Linux Rolling'"
      vw.vmx["sound.fileName"] = "-1"
      vw.vmx["annotation"] = "Kali Rolling (2021.4a) x64|0D|0A2021-12-19|0D|0A|0D|0A- - - - - - - - - - - - - - - - - -|0D|0A|0D|0AUsername: kali|0D|0APassword: kali|0D|0A(US keyboard layout)|0D|0A|0D|0A- - - - - - - - - - - - - - - - - -|0D|0A|0D|0A* Kali Homepage:|0D|0Ahttps://www.kali.org/|0D|0A|0D|0A* Documentation:|0D|0Ahttps://www.kali.org/docs/|0D|0A|0D|0A* Kali Tools:|0D|0Ahttps://www.kali.org/tools/|0D|0A|0D|0A* Forum/Community Support:|0D|0Ahttps://forums.kali.org/|0D|0A|0D|0A* IRC Channel: |0D|0Aircs://irc.oftc.net:6697/#Kali-Linux|0D|0Ahttps://www.kali.org/docs/community/kali-linux-irc-channel/|0D|0A|0D|0A"
      vw.vmx["ide1:0.autodetect"] = "TRUE"
      vw.vmx["ide1:0.startConnected"] = "FALSE"
      vw.vmx["usb:0.present"] = "TRUE"
      vw.vmx["usb:0.deviceType"] = "hid"
      vw.vmx["usb:0.port"] = "0"
      vw.vmx["usb:0.parent"] = "-1"
      vw.vmx["mks.enable3d"] = "TRUE"
      vw.vmx["gui.fitGuestUsingNativeDisplayResolution"] = "TRUE"
    end
  else
    # VIRUTALBOX SETTINGS
    config.vm.provider VIRTUALBOX do |vb|
      vb.name = VM_NAME
      vb.cpus = VM_CPUS
      vb.memory = VM_MEMORY
      vb.customize ["modifyvm", :id, "--vram", "256"]
      vb.customize ["modifyvm", :id, "--accelerate3d", "on"]
    end
  end

  # Ansible provisioner.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "site.yml"
  end
end
