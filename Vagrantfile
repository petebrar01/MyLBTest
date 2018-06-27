# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|
 	config.vm.box = "hashicorp/precise32"

	config.vm.provider "virtualbox" do |v|
 		v.memory = 1024
  		v.cpus = 1
	end

	config.vm.define "lb" do |config|
		config.vm.hostname = "lb"
	  	config.vm.network "private_network", ip: "10.10.10.10"
 		config.vm.provision :shell, path: "bootstrap-haproxy.sh"
	end

	config.vm.define "web1" do |config|
		config.vm.hostname = "web1"
	  	config.vm.network "private_network", ip: "10.10.10.11"
 		config.vm.provision :shell, path: "bootstrap-apache.sh"
	end

	config.vm.define "web2" do |config|
		config.vm.hostname = "web2"
	  	config.vm.network "private_network", ip: "10.10.10.12"
 		config.vm.provision :shell, path: "bootstrap-apache.sh"
	end

end
