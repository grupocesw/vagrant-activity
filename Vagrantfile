$default_network_interface = `ip route | awk '/^default/ {printf "%s", $5; exit 0}'`

Vagrant.configure("2") do |config|

  # Name box
  config.vm.define "vm-mysql"
 
  # Name in virtual box
  config.vm.provider :virtualbox do |vb|
      vb.name = "mysql"
  end

  # Operation system
  config.vm.box = "ubuntu/bionic64"

  # Public access by ip network
  config.vm.network "public_network", guest: 3306, host: 3306, ip: "192.168.10.115", bridge: "#$default_network_interface"

  config.vm.synced_folder "./data", "/vagrant_data"

  # Resource memory fixed
  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.memory = "1024"
  end

  # Provision external file
  config.vm.provision "bootstrap", type: "shell", path: "bootstrap.sh", run: 'once'

  # Provision inline
  config.vm.provision "specific-shell", type: "shell", run: 'always',
    inline: "echo run my shell command inline named..."

end
