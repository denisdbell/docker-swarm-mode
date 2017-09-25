# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "boxcutter/ubuntu1610"
    config.vm.provision "shell", path: "provision/node.sh", privileged: true

    # Managers
   config.vm.define "Master" do |node|
            node.vm.network "private_network", ip: "192.168.99.201"
            node.vm.hostname = "Master"
    end  
   
    # Workers
    (1..3).each do |number|
        config.vm.define "Worker#{number}" do |node|
            node.vm.network "private_network", ip: "192.168.99.21#{number}"
            node.vm.hostname = "Worker#{number}"
        end  
    end

    config.vm.provider "virtualbox" do |v|
        v.memory = 2048 
        v.cpus = 1
    end

end
