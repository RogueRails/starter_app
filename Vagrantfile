# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "roguerails-box"
  # Commenting this out since we don't want to download it over the net at the workshop
  # config.vm.box_url = "http://goo.gl/f27geQ"

  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :forwarded_port, guest: 3306, host: 3305
  config.vm.network :private_network, ip: "192.168.10.10"
  config.vm.synced_folder ".", "/vagrant", id: "vagrant-root", nfs: true

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", ENV['VAGRANT_CUSTOM_MEMORY'] || "1024" ]
  end
end
