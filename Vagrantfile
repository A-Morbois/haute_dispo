# -*- mode: ruby -*-
# # vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "coreos"
  config.vm.box_url = "http://storage.core-os.net/coreos/amd64-generic/dev-channel/coreos_production_vagrant.box"

  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end

  config.vm.network :forwarded_port, guest: 80, host: 5080
  config.vm.network :forwarded_port, guest: 8080, host: 8080
  config.vm.network :forwarded_port, guest: 5432, host: 5432

  config.vm.provision "shell", privileged: false, inline: "git clone https://github.com/A-Morbois/haute_dispo_dockerfile"
  

end
