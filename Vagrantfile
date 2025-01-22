# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_SERVER_URL'] = 'https://vagrant.elab.pro'

Vagrant.configure("2") do |config|
  

  config.vm.box = "ubuntu/jammy64"
  config.vm.box_check_update = false
  config.vm.network "public_network"
  config.vm.provider "virtualbox" do |vb|
  
     vb.gui = false
  
     vb.memory = "8192"
     vb.cpus = "4"
     vb.name = "docker"
  end
   
  config.vm.provision "shell", inline: <<-SHELL
      	apt-get update
	apt-get install ca-certificates curl -y
	install -m 0755 -d /etc/apt/keyrings
	curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
        chmod a+r /etc/apt/keyrings/docker.asc
	echo \
  		"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  		$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  		sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
	apt-get update
	apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
	docker pull nginx:1.21.3-alpine
	docker build -t alpine /vagrant
	docker run -d --name nginx-alpine --network=host alpine   
  SHELL
end
