vagrant_version = "2"

Vagrant.configure(vagrant_version) do |config|

  config.vm.define "elas" do |elas|

     elas.vm.box = "generic/ubuntu1804"
     elas.vm.hostname= "ub01elk"
     elas.vm.box_check_update = false
     elas.vm.network "forwarded_port", guest: 80, host: 8080
     elas.vm.network "private_network", ip: "192.168.56.103"
     elas.vm.network "public_network"

     elas.vm.provider "virtualbox" do |vb|
       vb.gui = true
       vb.name= "ub01elk"
       vb.memory = "2048"
     end

     elas.vm.provision "shell", inline: <<-SCRIPT
       echo Installing pre-requisites at `hostname`
       sudo apt-get -y update;
       sudo apt-get install -y software-properties-common python-apt;
       sudo apt-add-repository ppa:ansible/ansible;
       sudo apt-get -y update;
       sudo apt-get install -y sudo wget --allow-unauthenticated;
       sudo apt-get install -y python --allow-unauthenticated;
       sudo apt install -y ansible --allow-unauthenticated;
     SCRIPT
  end
  
  # config.vm.provision "ansible" do |ansible|
  #   ansible.host_key_checking = false
  #   ansible.limit = "all"
  #   ansible.config_file = 'ansible/ansible.cfg'
  #   ansible.inventory_path = "inventory.vagrant"
  #   ansible.playbook = "ansible/play.role.yml"
  # end

end
