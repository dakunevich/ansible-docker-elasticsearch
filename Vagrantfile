# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Base VM OS configuration.
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.synced_folder '.', '/vagrant', disabled: true

  # General VirtualBox VM configuration.
  config.vm.provider :virtualbox do |v|
    v.memory = 1536
    v.cpus = 2
    v.linked_clone = true
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  # node-01.
  config.vm.define "node01" do |node01|
    node01.vm.hostname = "node-01.local"
    node01.vm.network :private_network, ip: "192.168.2.11"
    # 
    node01.vm.provider :virtualbox do |v|
        v.name = "node-01"
    end
  end

  # node-02.
  config.vm.define "node02" do |node02|
    node02.vm.hostname = "node-02.local"
    node02.vm.network :private_network, ip: "192.168.2.12"
    # 
    node02.vm.provider :virtualbox do |v|
        v.name = "node-02"
    end
  end

  # node-03.
  config.vm.define "node03" do |node03|
    node03.vm.hostname = "node-03.local"
    node03.vm.network :private_network, ip: "192.168.2.13"
    # 
    node03.vm.provider :virtualbox do |v|
        v.name = "node-03"
    end
  end

  # node-04.
  config.vm.define "node04" do |node04|
    node04.vm.hostname = "node-04.local"
    node04.vm.network :private_network, ip: "192.168.2.14"
    # 
    node04.vm.provider :virtualbox do |v|
        v.name = "node-04"
    end
  end

  # node-01.
  config.vm.define "node05" do |node05|
    node05.vm.hostname = "node-05.local"
    node05.vm.network :private_network, ip: "192.168.2.15"
    # 
    node05.vm.provider :virtualbox do |v|
        v.name = "node-05"
    end
        # Run Ansible provisioner once for all VMs at the end.
    node05.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.inventory_path = "inventories/hosts"
      ansible.limit = "all"
      ansible.extra_vars = {
        ansible_ssh_user: 'vagrant',
        ansible_ssh_private_key_file: "~/.vagrant.d/insecure_private_key"
    }
    end
  end  
end
