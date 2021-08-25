Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/focal64"

    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
    end

    config.vm.define "docker" do |d|
        d.vm.network "public_network", bridge: "ens5", ip: "10.11.0.48"
        d.vm.provision "shell", inline: "cat /vagrant/id_rsa.pub >> /home/vagrant/.ssh/authorized_keys"
        d.name = "docker+jenkins"
    end

  
end