# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
    # Base VM OS configuration.
    config.vm.box = "ubuntu/bionic64"
    config.ssh.insert_key = false # Avoid  vagrant to remove the common ssh private key
    config.vm.provider :virtualbox do |v|
      v.memory = 1536
    end

    # elastic-node1
    config.vm.define "elastic_node1" do |elastic_node1|
      elastic_node1.vm.hostname = "elastic-node1"
      elastic_node1.vm.network :private_network, ip: "192.168.2.2"
    end

    # elastic_node2
    config.vm.define "elastic_node2" do |elastic_node2|
      elastic_node2.vm.hostname = "elastic-node2"
      elastic_node2.vm.network :private_network, ip: "192.168.2.3"
    end
      

    # nginx_node
    config.vm.define "nginx_node" do |nginx_node|
      nginx_node.vm.hostname = "nginx-node"
      nginx_node.vm.network :private_network, ip: "192.168.2.10"
    end
    

    # kibana-node
    config.vm.define "kibana_node" do |kibana_node|
      kibana_node.vm.hostname = "kibana-node"
      kibana_node.vm.network :private_network, ip: "192.168.2.4"
      
      # Run Ansible provisioner once for all VMs at the end i.e. for the last VM.
      kibana_node.vm.provision "ansible" do |ansible|
        ansible.playbook = "ping.yml"
        ansible.inventory_path = "hosts.cfg"
        ansible.limit = "all"
      end
    end

end
