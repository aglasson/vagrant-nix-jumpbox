# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure("2") do |config|
    config.vm.define "jumpbox"
    config.vm.box = "hashicorp/bionic64"
    config.vm.box_version = "1.0.282"
    config.vm.provision "file", source: ENV['USERPROFILE'] + "\\Documents\\Keys\\" + ENV['USERNAME'].downcase + "_private.ssh", destination: "/tmp/id_rsa"
    config.vm.provision "file", source: ENV['USERPROFILE'] + "\\Documents\\Keys\\" + ENV['USERNAME'].downcase + "_public.pub", destination: "/tmp/ssh_authorised.pub"
    config.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "/vagrant/vagrant-utils/ansible-provisioning.yml"
        ansible.extra_vars = {
            username: ENV['USERNAME'].downcase
        }
    end
    if ARGV[0] == "ssh"
        config.ssh.username = ENV['USERNAME'].downcase
        config.ssh.private_key_path = ENV['USERPROFILE'] + "\\Documents\\Keys\\" + ENV['USERNAME'].downcase + "_private.ssh"
    end
end