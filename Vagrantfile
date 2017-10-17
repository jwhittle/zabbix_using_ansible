# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
	config.vm.define "acs" do |acs|
		acs.vm.box = "ubuntu/xenial32"
		acs.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
		acs.vm.network "private_network", ip: "192.168.10.100"
		acs.vm.network "public_network"
		acs.vm.provider "virtualbox" do |vb|
			vb.name = "acs"
			#vb.group = "TEST"
			#vb.gui = true
			#vb.memory = "1024"
	end
		
	acs.vm.provision "shell", inline: <<-SHELL

			
		sudo apt-get -y install software-properties-common
		sudo apt-add-repository ppa:ansible/ansible
		sudo apt-get update
		sudo apt-get -y install ansible
		SHELL
	end

end