# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|


  config.vm.box = "ubuntu/jammy64"


  config.vm.hostname = "Zabbix"


  config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  config.vm.network "forwarded_port", guest: 22, host: 2225, host_ip: "127.0.0.1", id: "ssh"


  config.vm.provider "virtualbox" do |vb|
    vb.name = "zabbix-ubuntu-22.04"
    vb.memory = "2048"
    vb.cpus = 2
  end

  
  config.vm.provision "file", source: "./config", destination: "/tmp/config"
 

  config.vm.provision "shell", path: "provision/install_zabbix.sh"

end