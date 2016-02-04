# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "rbenigno/centos7"

  #config.vm.synced_folder ".", "/vagrant", disabled: true

  # Provision with Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.sudo = true
    ansible.groups = {
      "syslog-forwarders" => ["default"]
    }
  end

end
