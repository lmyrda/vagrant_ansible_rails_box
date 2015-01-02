# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define :web do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.network :private_network, ip: "10.33.33.33"
    web.vm.network :forwarded_port, guest: 80, host: 8080
    config.vm.synced_folder './rails-app', '/home/vagrant/apps/rails-app', id: "vagrant-root",
      owner: "vagrant",
      group: "www-data",
      mount_options: ["dmode=775,fmode=666"]
    web.vm.hostname = "rails-app.dev"

    web.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "1024"]
    end

    web.vm.provision :ansible do |ansible|
      ansible.playbook = "vagrant-build-server.yml"
      ansible.inventory_path = "hosts-vagrant"
      ansible.verbose = "v"
      ansible.ask_sudo_pass = true

      # https://github.com/mitchellh/vagrant/issues/3096
      ansible.limit = 'all'
    end

  end


end
