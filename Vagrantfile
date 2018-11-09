# sisinit Lab.
# Version: v1.0
# Author: Fabiano Santos Florentino
#
# Vagrantfile para criar ambiente de teste do programa sisinit.

Vagrant.configure(2) do |config|

  # maquina central para configuracao do ansible
  config.vm.define "sisinit" do |sis|
    sis.vm.box = "centos/7"
    sis.vm.hostname = "sisinit-staging"
    sis.vm.network "private_network", ip: "172.28.128.10"
    sis.vm.provider "virtualbox" do |rs|
      rs.memory = 1024
      rs.cpus = 2
    end
    sis.vm.provision "shell", inline: <<-SHELL

      RUN_WEB="https://gitlab.com/projects-shellscripts/sisinit/raw/master/run_web"
      curl -fsSL  ${RUN_WEB} | bash
    SHELL
  end
end