Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"

  config.vm.network "private_network", ip: "192.168.21.100"

  config.vm.provider "vmware_desktop" do |vb|
    vb.gui = false
    vb.vmx["memsize"] = "4096"
    vb.vmx["numvcpus"] = "2"
  end
  
  # Hostname
  config.vm.hostname = "jenkin-server"

  config.vm.provision "shell", inline: <<-SHELL
    apt update
    apt dist-upgrade -y
    apt autoclean
    apt autoremove -y
  SHELL

end
