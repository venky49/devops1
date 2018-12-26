
  Vagrant.configure("2") do |config|
  config.ssh.username = 'root'
  config.ssh.password = 'vagrant'
  config.ssh.insert_key = 'true'

  config.vm.define "web" do |web|
    web.vm.box = "bento/centos-7.2"
    web.vm.hostname = 'webserver'
    web.vm.box_url = "https://app.vagrantup.com/bento/boxes/centos-7.2"
  #  config.vm.provision :shell, :path => "bootstrap.sh"

    web.vm.network :private_network, ip: "192.168.56.2"
    web.vm.network "forwarded_port", guest: 80, host: 4567

    web.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "webserver"]
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "bento/centos-7.2"
    db.vm.hostname = 'dbserver'
    db.vm.box_url = "https://app.vagrantup.com/bento/boxes/centos-7.2"

    db.vm.network :private_network, ip: "192.168.56.3"

    db.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "dbserver"]
    end
  end

  config.vm.define "boss" do |boss|
    boss.vm.box = "bento/centos-7.2"
    boss.vm.hostname = 'boss'
    boss.vm.box_url = "https://app.vagrantup.com/bento/boxes/centos-7.2"

    boss.vm.network :private_network, ip: "192.168.56.4"
   # boss.vm.synced_folder "./Vagrant-demo", "./vagrant"

    boss.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "boss"]
    end
  end

 config.vm.define "master" do |master|
    master.vm.box = "bento/centos-7.2"
    master.vm.hostname = 'master'
    master.vm.box_url = "https://app.vagrantup.com/bento/boxes/centos-7.2"

    master.vm.network :private_network, ip: "192.168.56.5"
   # master.vm.synced_folder "./Vagrant-demo", "./vagrant"

    master.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "master"]
    end
  end


  config.vm.define "docker" do |docker|
    docker.vm.box = "bento/centos-7.2"
    docker.vm.hostname = 'docker'
    docker.vm.box_url = "https://app.vagrantup.com/bento/boxes/centos-7.2"

    docker.vm.network :private_network, ip: "192.168.56.6"
   # boss.vm.synced_folder "./Vagrant-demo", "./vagrant"

    docker.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "docker"]
    end
  end
end
