# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "digital_ocean"
	config.vm.box_url = "https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box"
	config.ssh.username = "leo"
	config.ssh.private_key_path = "~/.ssh/id_dsa"


  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  config.vm.provider "digital_ocean" do |provider|
		provider.client_id = '4224e246ef8aba7793a2354ce3c254d2'
		provider.api_key = '10d72487810ed22eda6581333590d04e'
    provider.image = "Ubuntu 14.04 x64"
    provider.region = "New York 2"
		provider.size = "512MB"
  end

  # Enable provisioning with Puppet stand alone.  Puppet manifests
  # are contained in a directory path relative to this Vagrantfile.
  # You will need to create the manifests directory and a manifest in
  # the file default.pp in the manifests_path directory.
  #
  config.vm.provision "puppet" do |puppet|
  	puppet.manifests_path = "manifests"
  	puppet.manifest_file  = "site.pp"
  end

end
