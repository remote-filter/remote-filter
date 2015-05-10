# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
    config.vm.box = "lalatendum/centos7-docker"
#    config.vm.synced_folder ".", "/home/vagrant", type: "rsync",
#                      rsync__exclude: [ ".git/", ".#*", "*~" ]
   config.vm.synced_folder "../rule-editor", "/home/vagrant/sync/rule-editor", type: "rsync",
                      rsync__exclude: [ ".git/", ".#*", "*~" ]
   config.vm.synced_folder "../rule-worker", "/home/vagrant/sync/rule-worker", type: "rsync",
                      rsync__exclude: [ ".git/", ".#*", "*~" ]
    #config.ssh.pty = true
    config.vm.provider :libvirt do |domain|
        domain.memory = 2048
        domain.cpus = 2
    end

    #config.vm.provision 'shell', inline: "ln -sf /mnt/host-projects/remote-filter/attempt-2 /home/vagrant/remote-filter"
    #config.vm.provision 'shell', inline: "curl -L https://github.com/docker/compose/releases/download/1.2.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose"
    #config.vm.provision 'shell', inline: "chmod +x /usr/local/bin/docker-compose"
    config.vm.provision 'shell', inline: "yum -y install http://mirror.redsox.cc/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm > /dev/null 2>&1 || :"
    config.vm.provision 'shell', inline: "yum -y install python python-pip"
    config.vm.provision 'shell', inline: "pip install -U docker-compose"
#    config.vm.provision 'shell', inline: "cd sync && docker-compose up -d"

end
