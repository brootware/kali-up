<p align="center">
<img src="https://i.imgur.com/pWf4nRB.png" />
<br />
<i>So many tools, so little time</i>
</p>

### About The Project

Kali-Up contains Ansible Roles to download and install additional frameworks, packages and stand-alone offensive utilities for a Kali Linux installation.
Downloading and installing are separate roles and not all tool have "installing" playbooks.

## Requirements

- [virtualbox](https://www.virtualbox.org/wiki/Downloads) OR [vmwarefusion](https://customerconnect.vmware.com/web/vmware/evalcenter?p=fusion-player-personal)
- [vagrant](https://www.vagrantup.com/docs/installation)
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-and-upgrading-ansible-with-pip)
- [Pip3](https://pip.pypa.io/en/stable/installation/)

## How to Use?

### Installing ansible roles without any virtualization

1. Clone this repo.

   ```
   git clone https://github.com/brootware/kali-up.git && cd kali-up
   ```

2. Modify [site.yml](./site.yml) to have the Ansible roles you want to install on your machine by commenting. Else all the roles will be installed.

   ```yaml
   roles:
     - c2-frameworks
     - re-frameworks
     - pwn-windows
     - pwn-linux
     - install-ghidra
     - chown-dirs
     - forensics-blue
   ```

3. Execute the following if you are installing it without any virtualization.

   ```bash
   ansible-playbook site.yml
   ```

### Installing ansible roles with Oracle Virtual Box

1. Makse sure to set ```USE_VMWARE``` variable in [Vagrantfile](./Vagrantfile) to false.

2. For having a disposable kali machine up and running via Oracle Virtual box, execute the following:

   ```bash
   vagrant up
   ```

3. The above should automatcally download latest kali image and install all the roles you specified.

   ```bash
   vagrant provision
   ```

4. Run the above command again if you ran into any issues.

### Installing ansible roles with VMWare Fusion. (do note this is still in development)

1. You will first need to install the Vagrant VMware provider plugin. [source](https://www.vagrantup.com/docs/providers/vmware/installation)

   ```bash
   vagrant plugin install vagrant-vmware-desktop
   ```

2. Download VMWare Vagrant Utility and install from [here](https://www.vagrantup.com/vmware/downloads).

3. Makse sure to set ```USE_VMWARE``` variable in [Vagrantfile](./Vagrantfile) to true.

4. Execute the following:

   ```bash
   vagrant up
   ```

_If there's errors, please open an issue!_

## Ansible Vars

The group vars specify the destination of RE, win-pwn, lin-pwn and C2 frameworks.
After downloading and installing, these directories (in /opt/ by default) are chown'd with the user running the script.

## Ansible Roles

#### C2-Frameworks

The `C2-Frameworks` role contains the c2 frameworks outlined in the [c2-matrix](https://howto.thec2matrix.com).
Note, this role just clones the repos but does not do any additional configuration for deployment. Seek stand-alone
roles for specific configuration. Frameworks within C2-matrix include the following

- [Mythic](https://www.github.com/its-a-feature/Mythic)
- [Caldera](https://www.github.com/mitre/caldera)
- [Covenant](https://www.github.com/cobbr/Covenant)
- [Empire](https://www.github.com/BC-SECURITY/Empire.git)
- [FactionC2](https://www.github.com/FactionC2/Faction) (Currently unpublished)
- [ibombshell](https://www.github.com/ElevenPaths/ibombshell.git)
- [Koadic](https://www.github.com/zerosum0x0/koadic)
- [Merlin](https://www.github.com/Ne0nd0g/merlin)
- [Nuages](https://www.github.com/p3nt4/Nuages)
- [PowerHub](https://github.com/AdrianVollmer/PowerHub.git)
- [SILENTTRINITY](https://github.com/byt3bl33d3r/SILENTTRINITY)
- [Silver](https://github.com/BishopFox/sliver)
- [TrevorC2](https://github.com/trustedsec/trevorc2.git)

#### RE-Frameworks

The `RE-Frameworks` role automates the downloading and installing of Ghidra and IDA Pro Free.
Note, you will be prompted to specify IDA install directory.

- [Ghidra](https://ghidra-sre.org/)
- [IDA Pro Free](https://www.hex-rays.com/products/ida/support/download_freeware/)
- [Cutter via Appimage](https://github.com/radareorg/cutter)
- [GDB Enhanced Framework](https://github.com/hugsy/gef)
- [Capstone Framework via pip](https://github.com/aquynh/capstone)
- [Unicorn Framework via pip](https://github.com/unicorn-engine/unicorn)
- [Keystone-Engine via pip](https://github.com/keystone-engine/keystone)
- [Ropper via pip](https://github.com/sashs/Ropper)
- [Pwntools via pip](https://github.com/Gallopsled/pwntools)

#### Win-PWN Tools

The `win-pwn` role automates the downloading of the following:

- [Bloodhound](https://github.com/BloodHoundAD/BloodHound)
- [Evil-WinRm](https://github.com/Hackplayers/evil-winrm)
- [CrackMapExec](https://github.com/byt3bl33d3r/CrackMapExec)
- [Unicorn](https://github.com/trustedsec/unicorn)
- [PowerSploit](https://github.com/PowerShellMafia/PowerSploit)
- [KeeTheif](https://github.com/GhostPack/KeeThief)
- [Seatbelt](https://github.com/GhostPack/Seatbelt)
- [SharpUp](https://github.com/GhostPack/SharpUp)
- [SafetyKatz](https://github.com/GhostPack/SafetyKatz)
- [SharpDump](https://github.com/GhostPack/SharpDump)
- [SharpWMI](https://github.com/GhostPack/SharpWMI)
- [Rubeus](https://github.com/GhostPack/Rubeus)
- [SharpDAPI](https://github.com/GhostPack/SharpDPAPI)
- [Lockless](https://github.com/GhostPack/Lockless)
- [SharpRoast](https://github.com/GhostPack/SharpRoast)

#### Lin-PWN Tools

The `lin-pwn` role automates the downloading of the following:

- [LinEnum](https://github.com/rebootuser/LinEnum)
- [GoBuster](https://github.com/OJ/gobuster)
- [MimiPenguin](https://github.com/huntergregal/mimipenguin)
- [LaZgne](https://github.com/AlessandroZ/LaZagne)
- [Pwndrop](https://github.com/kgretzky/pwndrop)
- [Reptile](https://github.com/f0rb1dd3n/Reptile)
- [Vlany](https://github.com/mempodippy/vlany)
- [Azazel](https://github.com/chokepoint/azazel)
- [Jynx2](https://github.com/chokepoint/Jynx2)
- [Jynx](https://github.com/chokepoint/jynxkit)
- [Apache-Rootkit](https://github.com/ChristianPapathanasiou/apache-rootkit)
- [Suterusu](https://github.com/mncoppola/suterusu)
- [Rooty](https://github.com/jermeyyy/rooty)
- [Diamorphine](https://github.com/m0nad/Diamorphine)

#### Forensic Blue Team Tools

- [foremost](https://salsa.debian.org/rul/foremost/tree/debian/sid)
- [exiftool](https://github.com/exiftool/exiftool)
- [steghide](https://salsa.debian.org/pkg-security-team/steghide)
- [oletools](http://decalage.info/python/oletools)
