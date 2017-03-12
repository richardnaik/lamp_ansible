VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Use the same key for each machine
  config.ssh.insert_key = false

  config.vm.define "vagrant-web" do |vagrant|
    vagrant.vm.box = "bento/centos-7.3"
    vagrant.vm.network "private_network", ip: "192.168.50.2"
    vagrant.vm.network "forwarded_port", guest: 80, host: 8080
    vagrant.vm.network "forwarded_port", guest: 443, host: 8443
  end

  config.vm.define "vagrant-db" do |vagrant|
    vagrant.vm.box = "bento/centos-7.3"
    vagrant.vm.network "private_network", ip: "192.168.50.3"
    vagrant.vm.network "forwarded_port", guest: 22, host: 2201
    vagrant.vm.network "forwarded_port", guest: 3306, host: 8306
  end
end