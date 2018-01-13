Vagrant.configure("2") do |config|
  config.vm.network "public_network", ip: "192.168.0.18"
  config.vm.define "web2" do |web2|
    web2.vm.box = "hashicorp/precise32"
	web2.vm.box_version = "1.0.0"
    web2.vm.hostname = 'drupal-web2'
    web2.vm.box_url = "hashicorp/precise32"
	 

    web2.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--cpus", 1]
      #v.customize ["modifyvm", :id, "--name", "kornel-web"]
      v.customize ["modifyvm", :id, "--nic2", "bridged"]
      v.customize ["modifyvm", :id, "--bridgeadapter2", "Realtek RTL8723AE Wireless LAN 802.11n PCI-E NIC"]
	  v.customize ["modifyvm", :id, "--paravirtprovider", "kvm"]
	  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"]
      #v.customize ["modifyvm", :id, "--bridgeadapter2", "enp0s25"]
      #v.customize ["modifyvm", :id, "--nic1", "nat"]
    end
    web2.vm.provision "shell", path: "web.sh"
  end

  config.vm.define "db2" do |db2|
    db2.vm.box = "hashicorp/precise32"
	db2.vm.box_version = "1.0.0"
    db2.vm.hostname = 'drupal-db2'
    db2.vm.box_url = "hashicorp/precise32"

    db2.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--cpus", 1]
      #v.customize ["modifyvm", :id, "--name", "kornel-db2"]
      v.customize ["modifyvm", :id, "--nic2", "bridged"]
      v.customize ["modifyvm", :id, "--bridgeadapter2", "Realtek RTL8723AE Wireless LAN 802.11n PCI-E NIC"]
	  v.customize ["modifyvm", :id, "--paravirtprovider", "kvm"]
	  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"]
      #v.customize ["modifyvm", :id, "--bridgeadapter2", "enp0s25"]
      #v.customize ["modifyvm", :id, "--nic1", "nat"]
    end
    db2.vm.provision "shell", path: "db.sh"
  end
end
