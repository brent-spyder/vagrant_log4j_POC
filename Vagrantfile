Vagrant.configure("2") do |config|
    config.vm.box = "brent-spyder/log4j_vulnerable"
    config.vm.define "vic" do |vic|
        vic.vm.hostname = "log4j_victim"
        vic.vm.network "forwarded_port", guest:8080, host:8080
        vic.vm.network "private_network", ip: "65.56.165.243"
        vic.memory = "2048"
    end
    config.vm.define "attk" do |attk|
        attk.vm.hostname = "log4j_attacker"
        attk.vm.network "private_network", ip: "65.56.165.10"
        attk.vm.provision "shell", path: "https://raw.githubusercontent.com/brent-spyder/vagrant_log4j_POC/main/attacker_setup.sh?token=GHSAT0AAAAAABNOMMJ5TMFFITTLGQHZX7AUYUECWOQ"
    end
end