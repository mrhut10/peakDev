# -*- mode: ruby -*-
# vi: set ft=ruby :
unless Vagrant.has_plugin?("vagrant-docker-compose")
  system("vagrant plugin install vagrant-docker-compose")
  puts "Dependencies installed, please try the command again."
  exit
end

$script = <<-SCRIPT
# updating packages
sudo apt-get -y -q update
# installing desktop GUI
sudo apt-get install -y xfce4 virtualbox-guest-dkms virtualbox-guest-utils virtualbox-guest-x11 
sudo sed -i 's/allowed_users=.*$/allowed_users=anybody/' /etc/X11/Xwrapper.config
##installing Container technology
## Dev tools
# git
apt-get install git
## installing browsers
# firefox
sudo apt-get -y install firefox
# chromium browser
sudo apt-get -y install code chromium-browser
## isntalling editors
# vs code
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'

SCRIPT


Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.synced_folder "./projects", "/projects"
  
  config.vm.network :forwarded_port, guest: 80, host: 8080, auto_correct: true
  config.vm.provider "virtualbox" do |v|
    v.name = "peakDev-VM"
    v.gui = true
    #v.customize ["modifyvm", :id, "--memory", "2048", "--cpus", "2", "--monitorcount", "2"]
    v.customize ["modifyvm", :id, "--memory", "2048", "--cpus", "2"]
  end

  config.vm.provision :docker
  config.vm.provision :docker_compose
  config.vm.provision :shell, inline: $script
end
