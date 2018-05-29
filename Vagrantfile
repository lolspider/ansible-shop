Vagrant.configure("2") do |config|
  config.vm.box = "wvera/sles12sp1"
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end
  config.vm.box_check_update = false

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "environment.yml"
  end

  config.vm.define :test do |test|
    test.vm.network  :private_network, ip: "192.168.34.110"
  end

  config.vm.define :prod do |prod|
    prod.vm.network  :private_network, ip: "192.168.35.110"
  end

  config.vm.define :jenkins do |jenkins|
    jenkins.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
    jenkins.vm.network  :private_network, ip: "192.168.34.112"
    jenkins.vm.network  :private_network, ip: "192.168.35.112"
  end

  config.vm.define :logserver do |logserver|
    logserver.vm.provider "virtualbox" do |v|
      v.memory = 5120
    end
    logserver.vm.network  :private_network, ip: "192.168.34.115"
    logserver.vm.network  :private_network, ip: "192.168.35.115"
  end
end
