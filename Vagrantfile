Vagrant.configure("2") do |config|
    config.vm.box = "brent-spyder/log4j_vulnerable"
    config.vm.define "vic" do |vic|
        vic.vm.hostname = "log4j-victim"
        vic.vm.network "forwarded_port", guest:8080, host:8080
        vic.vm.network "private_network", ip: "65.56.165.243"
        vic.vm.provision "shell", path: "./victim_setup.sh"
        vic.vm.provider "virtualbox" do |vb|
            vb.memory = "2048"
        end
    end
    config.vm.define "attk" do |attk|
        attk.vm.hostname = "log4j-attacker"
        attk.vm.network "private_network", ip: "65.56.165.10"
        attk.vm.provision "shell", path: "./attacker_setup.sh"
        attk.vm.provider "virtualbox" do |vb|
            vb.memory = "2048"
        end
    end
end