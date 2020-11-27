<p align="center">
<img src="https://i.imgur.com/pWf4nRB.png" />
<br />
<i>So many tools, so little time</i>
</p>

### About The Project
Kali-Up contains Ansible Roles to install additional frameworks and packages for a Kali Linux installation.

## Requirements
* Ansible
* pip3

## Ansible Vars
The group vars specify the destination of RE, win-pwn, lin-pwn and C2 frameworks.
After downloading and installing, these directories (in /opt/ by default) are chown'd with the user running the script.

## Ansible Roles
#### C2-Frameworks
The ```C2-Frameworks``` role contains the c2 frameworks outlined in the [c2-matrix](https://howto.thec2matrix.com).
Note, this role just clones the repos but does not do any additional configuration for deployment. Seek stand-alone
roles for specific configuration. Frameworks within C2-matrix include the following

* [Apfell](https://www.github.com/its-a-feature/Apfell)
* [Caldera](https://www.github.com/mitre/caldera)
* [Covenant](https://www.github.com/cobbr/Covenant)
* [Empire](https://www.github.com/BC-SECURITY/Empire.git)
* [FactionC2](https://www.github.com/FactionC2/Faction)
* [ibombshell](https://www.github.com/ElevenPaths/ibombshell.git)
* [Koadic](https://www.github.com/zerosum0x0/koadic)
* [Merlin](https://www.github.com/Ne0nd0g/merlin)
* [Nuages](https://www.github.com/p3nt4/Nuages)
* [PowerHub](https://github.com/AdrianVollmer/PowerHub.git)
* [SILENTTRINITY](https://github.com/byt3bl33d3r/SILENTTRINITY)
* [Silver](https://github.com/BishopFox/sliver)
* [TrevorC2](https://github.com/trustedsec/trevorc2.git)

#### RE-Frameworks
The ```RE-Frameworks``` role automates the downloading and installing of Ghidra and IDA Pro Free.
Note, you will be prompted to specify IDA install directory.
* [Ghidra](https://ghidra-sre.org/)
* [IDA Pro Free](https://www.hex-rays.com/products/ida/support/download_freeware/)
* [GDB Enhanced Framework](https://github.com/hugsy/gef)


#### Win-PWN Tools
The ```win-pwn``` role automates the downloading of the following:
* [Bloodhound](https://github.com/BloodHoundAD/BloodHound)
* [Evil-WinRm](https://github.com/Hackplayers/evil-winrm)
* [CrackMapExec](https://github.com/byt3bl33d3r/CrackMapExec)
* [Unicorn](https://github.com/trustedsec/unicorn)

#### Lin-PWN Tools
The ```lin-pwn``` role automates the downloading of the following:
* [LinEnum](https://github.com/rebootuser/LinEnum)
