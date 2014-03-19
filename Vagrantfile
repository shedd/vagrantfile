# -*- mode: ruby -*-
# vi: set ft=ruby :

CUSTOM_CONFIG = {
                  "BOX_NAME"  =>  "precise64", 
                  "BOX_URL"   =>  "http://files.vagrantup.com/precise64.box", 
                  "HEADLESS"  =>  false
                }

Vagrant.configure("2") do |config|
  # Change this to the name of your Vagrant base box.
  config.vm.box = CUSTOM_CONFIG['BOX_NAME']

  # Change this to a URL from which the base box can be downloaded, if you like.
  config.vm.box_url = CUSTOM_CONFIG['BOX_URL']

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network :private_network, ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network :public_network, ip: "10.0.1.11"

  # Create a forwarded port mapping which allows access to a specific port
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :forwarded_port, guest: 5432, host: 5432 # forward postgres
  config.vm.network :forwarded_port, guest: 3306, host: 3306 # forward mysql

  # headless?  uncomment this to have the VM's window available
  config.vm.provider :virtualbox do |vb|
    vb.gui = CUSTOM_CONFIG['HEADLESS']
  end

  # forward SSH keys
  # If true, then any SSH connections made will enable agent forwarding.
  config.ssh.forward_agent = true

  # provisioning with ansible
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "./ansible/playbook.yml"
    #ansible.verbose = "vvvv"
  end
end
