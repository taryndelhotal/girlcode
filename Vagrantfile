# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  # Synced folders
  config.vm.synced_folder ".", "/vagrant", type: "nfs"

  # Host only network required for NFS
  config.vm.network :forwarded_port, guest: 22, host: 2223
  config.vm.network :private_network, ip: "10.12.13.18"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning.yml"
  end
end
