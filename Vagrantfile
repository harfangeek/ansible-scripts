
Vagrant.configure(2) do |config|

  # VM name
  config.vm.box = "usine_logicielle"

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

  # Port forwarding
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Virtualbox provider
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end
  
  # Provision with ansible script
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "install_all.yml"
  end

end
