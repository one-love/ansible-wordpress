# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.define "wordpress" do |onelove|
        onelove.vm.box = "lugons"
        onelove.vm.box_url = "ftp://ftp.lugons.org/vagrant/debian-7.6.0-x86_64.box"
        onelove.vm.network :private_network, ip: "192.168.33.33"
        onelove.vm.provision :ansible do |ansible|
            ansible.playbook = "provision/site.yml"
            ansible.host_key_checking = false
            ansible.groups = {
                "vagrant" => ["wordpress"],
            }
        end
    end
end
