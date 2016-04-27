# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "rbenigno/centos7"

  # config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.define "srv1" do |node|
    node.vm.hostname = "srv1"
    # node.vm.provider "vmware_fusion" do |v|
    #   v.vmx["numvcpus"] = "1"
    #   v.vmx["memsize"] = "2048"
    # end
  end

  config.vm.define "hvy1" do |node|
    node.vm.hostname = "hvy1"
    # node.vm.provider "vmware_fusion" do |v|
    #   v.vmx["numvcpus"] = "1"
    #   v.vmx["memsize"] = "2048"
    # end
  end

  config.vm.define "ufw1" do |node|
    node.vm.hostname = "ufw1"
    # node.vm.provider "vmware_fusion" do |v|
    #   v.vmx["numvcpus"] = "1"
    #   v.vmx["memsize"] = "2048"
    # end
  end

  # Provision with Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.sudo = true
    ansible.groups = {
      "splunk-servers"       => ["srv1"],
      "heavy-forwarders"     => ["hvy1"],
      "universal-forwarders" => ["ufw1"],
      "syslog-collector"     => ["srv1"]
    }
  end

end
