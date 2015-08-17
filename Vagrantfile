# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.define "wordpress" do |wordpress|
        wordpress.vm.box = "debian-8.0"
        wordpress.vm.box_url = "ftp://ftp.lugons.org/vagrant/debian-8.0-x86_64.box"
        wordpress.vm.network :private_network, ip: "192.168.33.33"
        wordpress.vm.provider "virtualbox" do |v|
            v.memory = 1024
        end
        wordpress.vm.provision :ansible do |ansible|
            ansible.playbook = "provision/site.yml"
            ansible.host_key_checking = false
            ansible.groups = {
                "vagrant" => ["wordpress"],
            }
        end
    end
end
