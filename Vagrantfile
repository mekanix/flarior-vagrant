# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.define "flarior" do |flarior|
        flarior.vm.box = "debian-8.0"
        flarior.vm.box_url = "ftp://ftp.lugons.org/vagrant/debian-8.0-x86_64.box"
        flarior.vm.network :private_network, ip: "192.168.7.10"
        flarior.vm.hostname = "vagrant.flarior.com"
        flarior.vm.provision :ansible, run: "always" do |ansible|
            ansible.playbook = "provision/site.yml"
            ansible.host_key_checking = false
            ansible.groups = {
                "vagrant" => ["flarior"],
            }
        end
    end
end
