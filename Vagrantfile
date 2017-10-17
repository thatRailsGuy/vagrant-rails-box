Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"
    config.vm.box_version = "20171011.0.0"
    config.vm.network :forwarded_port, guest: 3000, host: 2999, auto_correct: true
    config.vm.synced_folder "./", "/var/www", create: true, group: "www-data", owner: "www-data"
    config.vm.provider "virtualbox" do |v|
        v.name = "Clint and Eric - Rails Box"
    end
    config.vm.provision :shell, path: "provision/install-rvm.sh", args: "stable", privileged: false
    config.vm.provision :shell, path: "provision/install-ruby.sh", args: "2.4.1 rails haml", privileged: false
    # config.vm.provision :shell, path: "provision/setup.sh", privileged: false
end