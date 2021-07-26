# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "galaxy3/bespin"
  config.vm.box_version = "2020.12.15-2048"
#  config.vm.hostname = "owaspbwa"
#  config.vm.box_version = '1.2.0'
  config.ssh.username = 'root'
  config.ssh.password = 'owaspbwa'

#  config.vm.network "private_network", ip: "10.55.56.101",
#    virtualbox__intnet: "metasploitable3", nic_type: "virtio"

#  config.vm.network "private_network", type: "dhcp"
#    name: "vboxnet3"

#  config.ssh.host "10.0.2.5"
#  config.ssh.port "22"
  config.vbguest.auto_update = false
  config.ssh.insert_key = false
  config.ssh.connect_timeout = 120
  config.vm.boot_timeout = 240
  config.vm.base_address = '10.0.2.15'

  config.trigger.after :up do |trigger|
    trigger.name = "Complete Setup"
  	trigger.info = File.read("Description")
  end

  config.vm.synced_folder ".", "/vagrant", disabled: true
#  config.vm.synced_folder	"../../",	"/vagrant", owner: "1001", group: "1001"
#  config.vm.synced_folder "~/repos/uci", "/repos", owner: "1001", group: "1001", mount_options: ["fmode=777", "dmode=777"], create: true
#  config.vm.synced_folder "../../Downloads", "/Downloads", owner: "1001", group: "1001", mount_options: ["fmode=777", "dmode=777"], create: true
  #config.vm.synced_folder "../../log/nakadia", "/var/log/", owner: "1001", group: "1001", mount_options: ["fmode=777", "dmode=777"], create: true

  config.vm.network "forwarded_port", guest: 22, host: 2200, id: "ssh", disabled: true
  config.vm.network "forwarded_port", guest: 22, host: 51022, host_ip: "0.0.0.0", auto_correct: true
  config.vm.network "forwarded_port", guest: 80, host: 80, host_ip: "0.0.0.0", auto_correct: true
#  config.vm.network "forwarded_port", guest: 8000, host: 8000, host_ip: "127.0.0.1", auto_correct: true
#  config.vm.network "forwarded_port", guest: 80, host: 50080, host_ip: "0.0.0.0", auto_correct: true
#  config.vm.network "forwarded_port", guest: 3389, host: 3389, host_ip: "0.0.0.0", auto_correct: true
  #config.vm.network "forwarded_port", guest: 5901, host: 5901, host_ip: "127.0.0.1", auto_correct: true

#  config.vm.provision "file", source: "playbook.yml", destination: "playbook.yml"
#  config.vm.provision "file", source: "../../functions", destination: "functions/bin"
#  config.vm.provision "file", source: "hosts", destination: "hosts"
#  config.vm.provision "file", source: "requirements.yml", destination: "requirements.yml"



  config.vm.network "private_network", ip: "10.55.56.59",
  	virtualbox__intnet: "metasploitable3",
  	auto_config: false
#  	mac: "080027aaaaba"

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    # Uncomment ONE the lines below to control how much RAM Vagrant gives the VM
    # We recommend starting with 4096 (4Gb), and moving down if necessary
    # vb.memory = "1024" # 1Gb
    # vb.memory = "2048" # 2Gb
    # vb.memory = "4096" # 4Gb
    vb.name = "OWASPbwa"
    vb.gui = false
    vb.cpus = "2"
    vb.memory = "4096"
    #vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]

    #vb.customize ['modifyvm', :id, '--vrde', 'off']
    #vb.customize ['modifyvm', :id, '--vrdeaddress', '0.0.0.0']
    #vb.customize ['modifyvm', :id, '--vrdeport', '2200']
    #vb.customize ['modifyvm', :id, '--graphicscontroller', 'vboxsvga']
    #vb.customize ['modifyvm', :id, '--firmware', 'efi64']

#    vb.customize ['modifyvm', :id, '--nic0', 'intnet']
#    vb.customize ['modifyvm', :id, '--nictype0', 'Am79C960']
#    vb.customize ['modifyvm', :id, '--intnet0', 'metasploitable3']

#    vb.customize ['modifyvm', :id, '--nic1', 'intnet']
#    vb.customize ['modifyvm', :id, '--nictype1', 'Am79C960']
#    vb.customize ['modifyvm', :id, '--intnet1', 'metasploitable3']

#    vb.customize ['modifyvm', :id, '--nic2', 'intnet']
 #   vb.customize ['modifyvm', :id, '--nictype2', 'Am79C960']
 #   vb.customize ['modifyvm', :id, '--intnet2', 'metasploitable3']

  end
#  config.vm.provision "shell", inline: <<-SHELL
#     ifconfig eth1 10.55.56.101 netmask 255.255.255.0 up
     #egrep -v '^vagrant' /etc/shadow /etc/shadow.orig
     #cp /etc/shadow.orig /etc/shadow
     #echo 'vagrant:$6$DTNMrYnNBPQ9j2Wd$Ny8MCVaxCtGeDEeS.Me6mWl1HzobHl8RsbRiSfcfUm1eM78zsStNhZyVY7Q36gsRYh9tp8JUD/rd3mw.GmnZF.:18583:0:99999:7:::' >> /etc/shadow
#SHELL
#  config.vm.provision "ansible_local" do |ansible|
#    ansible.playbook = "/vagrant/vagrant/naboo/playbook.yml"
#    ansible.galaxy_role_file = "/home/vagrant/requirements.yml"
#    inventory_path = "/home/vagrant/hosts"
#  end
end