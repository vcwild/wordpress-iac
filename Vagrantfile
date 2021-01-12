Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/trusty64"

    config.vm.provider "virtualbox" do |v|
        v.name = "ubuntu_trusty_config"
        v.memory = 1024
        v.cpus = 2
    end

    config.vm.define "wordpress" do |wp|
        wp.vm.network "public_network", bridge: "enp0s25", ip: "192.168.15.153"
    end
end
    