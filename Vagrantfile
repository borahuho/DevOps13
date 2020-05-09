$useraddscript = <<SCRIPT
useradd -m henk
groupadd operators
usermod -aG operators henk
mkdir /operators
chown henk /operators
chgrp operators /operators
SCRIPT


Vagrant.configure('2') do |config|
    
    # set default settings
    config.vm.box = "ubuntu/bionic64"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 2048
        vb.cpus = 1
    end

    config.vm.define "ansible_host", primary: true do |machine1|
        machine1.vm.host_name = "ansible_host.local"
        machine1.vm.network "private_network", ip: "192.168.10.100"
        machine1.vm.provision "shell", inline: $useraddscript
        machine1.vm.provision :shell, path: "bootstrap.sh"
        machine1.vm.provider "virtualbox" do |vb|
            vb.cpus = 1
        end
        machine1.vm.synced_folder "DevOps13/", "/home/vagrant/mission"
    end

    config.vm.define "server1", primary: false do |machine2|
        machine2.vm.host_name = "server1.local"
        machine2.vm.network "private_network", ip: "192.168.10.105"
        machine2.vm.provision "shell", inline: $useraddscript
        machine2.vm.provider "virtualbox" do |vb|
            vb.cpus = 1
        end
    end

    config.vm.define "server2", primary: false do |machine3|
        machine3.vm.host_name = "server2.local"
        machine3.vm.network "private_network", ip: "192.168.10.110"
        machine3.vm.provision "shell", inline: $useraddscript
        machine3.vm.provider "virtualbox" do |vb|
            vb.cpus = 1
        end
    end
end