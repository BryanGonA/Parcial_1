Vagrant.configure("2") do |config|
    config.vm.network "forwarded_port", guest: 80, host: 7070
if Vagrant.has_plugin? "vagrant-vbguest"
config.vbguest.no_install = true
config.vbguest.auto_update = false
config.vbguest.no_remote = true
end
config.vm.define :cliente do |cliente|
cliente.vm.box = "centos/stream8"
config.vm.synced_folder ".","/home/vagrant/",type:"virtualbox"
cliente.vm.network :private_network, ip: "192.168.50.2"
cliente.vm.hostname = "cliente"


end
config.vm.define :servidor do |servidor|
servidor.vm.box = "centos/stream8"
config.vm.synced_folder ".","/home/vagrant/",type:"virtualbox"
servidor.vm.network :private_network, ip: "192.168.50.3"
servidor.vm.hostname = "servidor"
#config.vm.network "forwarded_port", guest: 80, host: 8080
end

end
