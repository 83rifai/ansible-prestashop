# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    # Every Vagrant virtual environment requires a box to build off of.
    config.vm.box = "hashicorp/precise64"

    config.vm.hostname = "srv01"

    config.vm.network "private_network", ip: "192.168.101.10"
    config.vm.network "forwarded_port", guest: 80, host: 8080
end
