Vagrant.configure("2") do |config|

  config.vm.define "etcd1" do |subconfig|
    subconfig.vm.box = "bento/centos-7.4"
    subconfig.vm.network "private_network", ip: "90.90.90.10"
    subconfig.vm.hostname = "etcd1.haribook.net"
    config.vm.provision "shell", inline: <<-SHELL
    sudo yum install -y etcd
    #sudo systemctl start etcd
    sudo echo "90.90.90.10 etcd1.haribook.net etcd1" >> /etc/hosts
    sudo echo "90.90.90.11 etcd2.haribook.net etcd2" >> /etc/hosts
    sudo echo "90.90.90.12 etcd3.haribook.net etcd3" >> /etc/hosts
    sudo mkdir -p /var/lib/etcd/
    sudo chown -R etcd:etcd /var/lib/etcd/
    sudo cp /vagrant/etcd1.service /etc/systemd/system/etcd.service
    SHELL

  end

  config.vm.define "etcd2" do |subconfig|
    subconfig.vm.box = "bento/centos-7.4"
    subconfig.vm.network "private_network", ip: "90.90.90.11"
    subconfig.vm.hostname = "etcd2.haribook.net"
    config.vm.provision "shell", inline: <<-SHELL
    sudo yum install -y etcd
    #sudo systemctl start etcd
    sudo echo "90.90.90.10 etcd1.haribook.net etcd1"  >> /etc/hosts
    sudo echo "90.90.90.11 etcd2.haribook.net etcd2"  >> /etc/hosts
    sudo echo "90.90.90.12 etcd3.haribook.net etcd3"  >> /etc/hosts
    sudo mkdir -p /var/lib/etcd/
    sudo chown -R etcd:etcd /var/lib/etcd/
    sudo cp /vagrant/etcd2.service /etc/systemd/system/etcd.service
    SHELL
  end

  config.vm.define "etcd3" do |subconfig|
    subconfig.vm.box = "bento/centos-7.4"
    subconfig.vm.network "private_network", ip: "90.90.90.12"
    subconfig.vm.hostname = "etcd3.haribook.net"
    config.vm.provision "shell", inline: <<-SHELL
    sudo yum install -y etcd
    #sudo systemctl start etcd
    sudo echo "90.90.90.10 etcd1.haribook.net etcd1"  >> /etc/hosts
    sudo echo "90.90.90.11 etcd2.haribook.net etcd2"  >> /etc/hosts
    sudo echo "90.90.90.12 etcd3.haribook.net etcd3"  >> /etc/hosts
    sudo mkdir -p /var/lib/etcd/
    sudo chown -R etcd:etcd /var/lib/etcd/
    sudo cp /vagrant/etcd3.service /etc/systemd/system/etcd.service
    SHELL
  end

end
