Vagrant.configure("2") do |config|
    config.vm.box = "debian/bookworm64"
    config.vm.box_check_update = false
    config.vm.synced_folder '.', '/vagrant', disabled: true
    config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 2
    end
    config.vm.define "plano-control" do |pcontrol|
      pcontrol.vm.hostname = "plano-control"
      pcontrol.vm.network "private_network",
        ip: "192.168.56.10"
    end
    config.vm.define "nodo1" do |nodo1|
      nodo1.vm.hostname = "nodo1"
      nodo1.vm.network "private_network",
        ip: "192.168.56.20"
    end
    config.vm.define "nodo2" do |nodo2|
      nodo2.vm.hostname = "nodo2"
      nodo2.vm.network "private_network",
        ip: "192.168.56.30"
    end
  end
