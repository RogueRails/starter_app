# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "story_tracker_test_box"
  #config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :private_network, ip: "192.168.10.10"
  config.vm.synced_folder ".", "/vagrant", id: "vagrant-root"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", ENV['VAGRANT_CUSTOM_MEMORY'] || "1024" ]
  end
end