# -*- mode: ruby -*-

Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.4"

  config.vm.network :private_network, ip: "192.168.33.110"
  config.vm.hostname = "dev-env.fuwalab"
  config.hostsupdater.aliases = [
      "dev-env.fuwalab",
      "php.dev-env.fuwalab",
      "go.dev-env.fuwalab",
  ]

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end
end
