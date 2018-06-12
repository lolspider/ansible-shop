Vagrant.configure("2") do |config|
  config.vm.box = "suse/sles12sp1"
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end
  config.vm.box_check_update = false
  config.ssh.insert_key = false

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "environment.yml"
  end

  config.vm.define :uat do |uat|
    uat.vm.network  :private_network, ip: "172.16.34.110"
  end

  config.vm.define :prod do |prod|
    prod.vm.network  :private_network, ip: "172.16.35.110"
  end

  config.vm.define :gocd do |gocd|
    gocd.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
    gocd.vm.network  :private_network, ip: "172.16.34.112"
    gocd.vm.network  :private_network, ip: "172.16.35.112"
  end

  config.vm.define :logserver do |logserver|
    logserver.vm.provider "virtualbox" do |v|
      v.memory = 5120
    end
    logserver.vm.network  :private_network, ip: "172.16.34.115"
    logserver.vm.network  :private_network, ip: "172.16.35.115"
  end
end
