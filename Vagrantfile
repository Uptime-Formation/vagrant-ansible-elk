Vagrant.configure("2") do |config|
    config.vm.synced_folder ".", "/vagrant", :disabled => true

    config.vm.provider :virtualbox do |v|
      v.memory = 8192
      v.cpus = 4
    end
    config.vm.define :kibana do |kibana|
        kibana.vm.box = "ubuntu/focal64"
        kibana.vm.hostname = "kibana"
        kibana.vm.network :private_network, ip: "10.0.2.6"
    end

    config.vm.define :node1 do |node1|
        node1.vm.box = "ubuntu/focal64"
        node1.vm.hostname = "node1"
        node1.vm.network :private_network, ip: "10.0.2.4"
      end


    config.vm.define :node2 do |node2|
        node2.vm.box = "ubuntu/focal64"
        node2.vm.hostname = "node2"
        node2.vm.network :private_network, ip: "10.0.2.5"
#         node2.vm.provision :shell, privileged: false, inline: <<-SHELL
#   sudo /vagrant/join.sh
#   SHELL
      end
  end
 

#   config.vm.provision "ansible" do |ansible|
#     ansible.verbose = "v"
#     ansible.playbook = "playbook.yaml"
#   end