# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    # Base VM OS configuration.
    config.vm.box = "ubuntu/bionic64"
    # config.vm.box = "geerlingguy/centos6"
    config.ssh.insert_key = false
    config.vm.synced_folder '.', '/vagrant', disabled: true
  
    # General VirtualBox VM configuration.
    config.vm.provider :virtualbox do |v|
      v.memory = 1024
      v.cpus = 1
    end
  
    # elk_node1.
    config.vm.define "elastic_node1" do |elastic_node1|
      elastic_node1.vm.hostname = "elastic-node1"
      elastic_node1.vm.network :private_network, ip: "192.168.2.2"
    end
  
    # elk_node1.
    config.vm.define "elastic_node2" do |elastic_node2|
      elastic_node2.vm.hostname = "elastic-node2"
      elastic_node2.vm.network :private_network, ip: "192.168.2.3"
    end
  
    # kibana_node.
    config.vm.define "kibana_node" do |kibana_node|
      kibana_node.vm.hostname = "kibana-node"
      kibana_node.vm.network :private_network, ip: "192.168.2.1"
  
      # Run Ansible provisioner once for all VMs at the end.
      kibana_node.vm.provision "ansible" do |ansible|
        ansible.playbook = "ping.yml"
        ansible.inventory_path = "hosts.cfg"
        ansible.limit = "all"
        ansible.extra_vars = {
          ansible_ssh_user: 'vagrant',
          ansible_ssh_private_key_file: "~/.vagrant.d/insecure_private_key"
        }
      end

    end

end
  