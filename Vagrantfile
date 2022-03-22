# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General Vagrant VM configuration.
  config.vm.box = 'ubuntu/focal64'
  config.ssh.insert_key = false
  config.vm.synced_folder '.', '/vagrant', disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.linked_clone = true
  end

  # Application server 1.
  config.vm.define 'app1' do |app|
    app.vm.hostname = 'app1.test'
    app.vm.network :private_network, ip: '192.168.56.4'
  end

  # Application server 2.
  config.vm.define 'app2' do |app|
    app.vm.hostname = 'app2.test'
    app.vm.network :private_network, ip: '192.168.56.5'
  end

  # Database server.
  config.vm.define 'db' do |db|
    db.vm.hostname = 'db.test'
    db.vm.network :private_network, ip: '192.168.56.6'
  end
end
