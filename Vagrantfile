
Vagrant.configure("2") do |config|
  # "dummy" box because we're using Glance
  config.vm.box = "hashicorp/precise32"

  # SSH
  #config.ssh.private_key_path = "/path/to/id_rsa"



  config.vm.provision "shell", :inline => <<-SHELL
    apt-get update
    apt-get install -y puppet
    #apt-get install -y apache2
    apt-get install -y curl
    #curl -sL https://deb.nodesource.com/setup | sudo bash -
    apt-get install -y nodejs
    apt-get install -y git
    chown 777 /var/www
    cd /var/www
    git clone https://github.com/francis-valbuena/open_layer3_sample.git
    cd /open_layer3_sample
    npm install
    npm start
  SHELL

  #config.vm.provision "puppet" do |puppet|
   # puppet.hiera_config_path = "hiera.yaml"
  #  puppet.module_path = "modules"
 # end

end