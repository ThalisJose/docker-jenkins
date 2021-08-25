# Environment Automation - Jenkins + Docker


  - Vagrant
  - Ansible

# Vagrant configurantion
- Provider: VirtualBox
- Operational System: Ubuntu 20.04.2.0 LTS
- Memory: 2GB
- Access SSH: Public key access mode
```python
Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/focal64"

    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
    end

    config.vm.define "docker" do |d|
        d.vm.network "public_network", bridge: "ens5", ip: "IP"
        d.vm.provision "shell", inline: "cat /vagrant/id_rsa.pub >> /home/vagrant/.ssh/authorized_keys"
    
    end  
end

```
Note: Alter IP value in vagrantfile




