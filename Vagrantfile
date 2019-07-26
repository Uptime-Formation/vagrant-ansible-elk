# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
    # Base VM OS configuration.
    config.vm.provider "virtualbox"
    config.vm.box = "ubuntu/bionic64"

    # elk_node1
    config.vm.define "elastic_node1" do |elastic_node1|
      elastic_node1.vm.hostname = "elastic-node1"
      elastic_node1.vm.network :private_network, ip: "192.168.2.2"
    end

    # elk_node1
    config.vm.define "elastic_node2" do |elastic_node2|
      elastic_node2.vm.hostname = "elastic-node2"
      elastic_node2.vm.network :private_network, ip: "192.168.2.3"
    end

end