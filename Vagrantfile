Vagrant.configure("2") do |config|

 config.vm.box = "Ubuntu-Server-14.04"

 config.vm.box_url = 'https://oss-binaries.phusionpassenger.com/vagrant/boxes/latest/ubuntu-14.04-amd64-vbox.box'

 config.ssh.forward_agent = true

 config.vm.network "private_network", ip:"192.168.50.5"
 config.vm.network "forwarded_port", guest: 8000, host: 8000
 config.vm.synced_folder ".", "/vagrant", disabled: true

  # project source code
  config.vm.synced_folder "./../mysite", "/var/www/mysite", owner: "www-data", group: "www-data"

  config.vm.provision "ansible" do |ansible|
  	  ansible.playbook = "site.yml"
  end

end
