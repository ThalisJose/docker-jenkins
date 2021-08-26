<h1 align="center">Environment Automation - Jenkins + Docker</h1>
<p align="center">Scenario created to streamline the deployment of a jenkins server in docker.</p>

# Tools used
 
<p align="left"> <a href="https://www.gnu.org/software/bash/" target="_blank"> <img src="https://www.vectorlogo.zone/logos/gnu_bash/gnu_bash-icon.svg" alt="bash" width="40" height="40"/> </a> <a href="https://www.docker.com/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="docker" width="40" height="40"/> </a> <a href="https://git-scm.com/" target="_blank"> <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="git" width="40" height="40"/> </a> <a href="https://www.jenkins.io" target="_blank"> <img src="https://www.vectorlogo.zone/logos/jenkins/jenkins-icon.svg" alt="jenkins" width="40" height="40"/> </a> <a href="https://www.linux.org/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="linux" width="40" height="40"/> </a> <a href="https://www.vagrantup.com/" target="_blank"> <img src="https://www.vectorlogo.zone/logos/vagrantup/vagrantup-icon.svg" alt="vagrant" width="40" height="40"/> </a> </p>


# Vagrant configuration
- Provider: VirtualBox
- Operational System: Ubuntu 20.04.2.0 LTS
- Memory: 2GB
- Access SSH: Public key access mode
<p align="center">Note: Alter IP value</p>

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



After the configuration file completes, run the command below to start creating the VM

```bash
vagrant up
```

## Author

👤 **Thalis José**

- Github: [@ThalisJose](https://github.com/ThalisJose)
