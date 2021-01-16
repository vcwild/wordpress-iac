Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/trusty64"

    config.vm.provider "virtualbox" do |v|
        v.name = "ubuntu_config"
        v.memory = 1024
        v.cpus = 2
    end

    config.vm.define "wordpress" do |wp|
        wp.vm.network "public_network", bridge: "enp0s25", ip: "192.168.15.153"
        
        wp.vm.provider "virtualbox" do |v|
            v.name = "ubuntu_wordpress"
        end

        wp.vm.provision "shell", 
            inline: "cat /vagrant/ssh-keys/vagrant_id_rsa.pub >> .ssh/authorized_keys"
    end

    config.vm.define "mysql" do |sql|
        sql.vm.network "public_network", bridge: "enp0s25", ip: "192.168.15.154"
        
        sql.vm.provider "virtualbox" do |v|
            v.name = "ubuntu_mysql"
        end
        
        sql.vm.provision "shell", 
        inline: "cat /vagrant/ssh-keys/vagrant_id_rsa.pub >> .ssh/authorized_keys"
    end
end
    