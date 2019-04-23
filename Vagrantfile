# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    end

    config.vm.box = "bento/ubuntu-18.04"

    config.vm.network "forwarded_port", guest: 8080, host: 8080

    config.vm.provision :ansible do |ansible|
        ansible.playbook = "playbook.yml"
    end

    config.ssh.forward_agent = true
    config.ssh.forward_x11 = true

end
