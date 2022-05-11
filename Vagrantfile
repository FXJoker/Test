# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
   config.vm.box = "generic/debian9"
   config.vm.hostname = "test"
   config.disksize.size = "10GB"
   config.vm.box_check_update = false
   config.ssh.username = "vagrant"
   config.ssh.password = "vagrant"
   config.ssh.keys_only = false
   config.vm.network "private_network", ip: "192.168.56.222"
   config.vm.provider "virtualbox" do |vb|
    vb.gui = false
     vb.name = "test"
     vb.memory = "2048"
     vb.cpus = 2
   end
   config.vm.provision  "php", type:'ansible' do |ansible|
      ansible.playbook = "php.yaml"
   end
   config.vm.provision  "install_packages", type:'ansible' do |ansible|
      ansible.playbook = "install_packages.yaml"
   end
   config.vm.provision  "apache", type:'ansible' do |ansible|
      ansible.playbook = "apache.yaml"
   end
   config.vm.provision  "nginx", type:'ansible' do |ansible|
      ansible.playbook = "nginx.yaml"
   end
#   config.vm.provision  "upgrade_php", type:'ansible' do |ansible|
#      ansible.playbook = "upgrade_php.yaml"
#   end
end
