# DevOps13

This vagrant will install 3 Linux Ubuntu machines, 2x node server and 1 ubuntu server with Ansible.
It will add some default users, groups and directory's.
This Vagrant is to practice with Ansible.
This repository is intended for educational purpose only.


## Prerequisites

Works on Windows 10 and tested on macOS (macOS needs the Virtualbox extension pack).

Software needed:
* Virtualbox 5.0 or higher
* Git bash for Windows
* Vagrant 2.2.6 or higher


## Demo installation && use Vagrant

Youtube: https://youtu.be/KABnIuaA8SM


## Demo Ansible

Youtube: https://youtu.be/8Gw5zuOhr5c


## Installation

* Install Virtualbox: https://www.virtualbox.org/wiki/Downloads
* Install Git bash for Windows: https://gitforwindows.org/
* Install Vagrant for Windows: https://www.vagrantup.com/downloads.html

## Run this Vagrant VM
Open **Git Bash** in Windows
```
cd Documents
mkdir vagrant && cd vagrant
git clone https://github.com/borahuho/DevOps13
cd DevOps13
vagrant up
vagrant ssh ansible
```
## Mission

Read your mission in ~/vagrant/mission (on Ansible server)

## Network
Vagrant VM will be set up with 2 network adapters
```
Nat : DHCP
Localhost (ansible): 192.168.10.100

Nat : DHCP
Localhost (server1): 192.168.10.105

Nat : DHCP
Localhost (server2): 192.168.10.110
```
## Vagrant commands
Start VM's with Vagrant
```
vagrant up
```
Pause a VM
```
vagrant suspend
```
Restart a paused VM
```
vagrant resume
```
Stop and shutdown a VM
```
vagrant halt
```
Remove a VM
```
vagrant destroy
```
ssh in to the VM
```
vagrant ssh ansible
vagrant ssh server1
vagrant ssh server2
```

