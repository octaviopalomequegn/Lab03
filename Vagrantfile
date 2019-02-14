# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
	config.vm.define "web" do |web|
		web.vm.box = "ubuntu/bionic64"
		web.vm.network "forwarded_port", guest: 80, host: 7080, host_ip: "127.0.0.1"
		web.vm.network "private_network", ip: "192.168.0.10"
		web.vm.provision "file", source:"C:/Users/Octavio/Desktop/10 semestre/Administracion de redes y servidores/Project1Clock", destination:"$HOME"
		web.vm.provision "shell", inline: <<-SHELL
			echo "webserver" > /etc/hostname
			hostname -b webserver
			echo "192.168.0.10		webserver" >> /etc/hosts
			sudo apt-get update
			sudo apt-get install -y nodejs npm
			nodejs --version
			npm --version
		SHELL
	end	
	
	config.vm.define "clock" do |clock|
		clock.vm.box = "ubuntu/bionic64"
		clock.vm.network "forwarded_port", guest: 81, host: 6080, host_ip: "127.0.0.1"
		clock.vm.network "private_network", ip: "192.168.0.20"
		clock.vm.provision "file", source:"C:/Users/Octavio/Desktop/10 semestre/Administracion de redes y servidores/Project1Clock", destination:"$HOME"
		clock.vm.provision "shell", inline: <<-SHELL
			echo "clock" > /etc/hostname
			hostname -b webserver
			echo "192.168.0.20		clock" >> /etc/hosts
			sudo apt-get update
			sudo apt-get install -y nodejs npm
			nodejs --version
			npm --version
		SHELL
	end	
end
