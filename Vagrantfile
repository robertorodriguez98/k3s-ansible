Vagrant.configure("2") do |config|
    config.vm.box = "debian/bookworm64"
    config.vm.box_check_update = false
    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.provider "libvirt" do |v|
      v.memory = 4096
      v.cpus = 4
      v.driver = "qemu"
    end
    config.vm.define "plano-control" do |pcontrol|
      pcontrol.vm.hostname = "plano-control"
      pcontrol.vm.network "private_network",
        :libvirt__network_name => "k3s-vagrant",
        :ip => "10.10.10.10",
        :libvirt__dhcp_enabled => false,
        :libvirt__forward_mode => "veryisolated"
    end
    config.vm.define "nodo1" do |nodo1|
      nodo1.vm.hostname = "nodo1"
      nodo1.vm.network "private_network",
        :libvirt__network_name => "k3s-vagrant",
        :ip => "10.10.10.20",
        :libvirt__dhcp_enabled => false,
        :libvirt__forward_mode => "veryisolated"
    end
    config.vm.define "nodo2" do |nodo2|
      nodo2.vm.hostname = "nodo2"
      nodo2.vm.network "private_network",
        :libvirt__network_name => "k3s-vagrant",
        :ip => "10.10.10.30",
        :libvirt__dhcp_enabled => false,
        :libvirt__forward_mode => "veryisolated"
    end
  end
