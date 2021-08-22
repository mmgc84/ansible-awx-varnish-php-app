# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/debian10"

  config.ssh.insert_key = false

  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.linked_clone = true
  end

  # App server 1
  config.vm.define "varnish" do |varnish|
    varnish.vm.hostname = "app1.test"
    varnish.vm.network :private_network, ip: "192.168.60.10"
  end

  # App server 2
  config.vm.define "php1" do |php1|
    php1.vm.hostname = "php1.test"
    php1.vm.network :private_network, ip: "192.168.60.11"
  end

  # DB server
  config.vm.define "php2" do |php2|
    php2.vm.hostname = "php2.test"
    php2.vm.network :private_network, ip: "192.168.60.12"
  end
end