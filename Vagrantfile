# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing...
Vagrant.configure(2) do |config|

  config.vm.define "acs" do |acs|
    acs.vm.box = "nrel/CentOS-6.5-x86_64"
    acs.vm.hostname = "acs"
    acs.vm.network "private_network", ip: "192.168.33.40"
	config.vm.synced_folder ".", "/vagrant"
	 config.vm.provision "ansible_local" do |ansible|
	 ansible.playbook = "playbook.yml"
	 end
  end

  config.vm.define "web" do |web|
    web.vm.box="nrel/CentOS-6.5-x86_64"
    web.vm.hostname = "web"
    web.vm.network "private_network", ip: "192.168.33.50"
    web.vm.network "forwarded_port", guest: 80, host: 8080
  end

  config.vm.define "db" do |db|
    db.vm.box = "nrel/CentOS-6.5-x86_64"
    db.vm.hostname = "db"
    db.vm.network "private_network", ip: "192.168.33.60"
  end

    config.vm.define "app" do |app|
    app.vm.box = "nrel/CentOS-6.5-x86_64"
    app.vm.hostname = "app"
    app.vm.network "private_network", ip: "192.168.33.70"
  end

end
