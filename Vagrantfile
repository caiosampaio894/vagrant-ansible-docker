Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1204
    vb.cpus = 2
    vb.name = "vagrant-ansible-docker"
  end
  
  config.vm.box = "hashicorp/bionic64"
  config.vm.hostname = "vagrant-ansible-docker"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "public_network", ip: "192.168.0.133", bridge: "enp2s0"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.ask_vault_pass = true
  end
end

