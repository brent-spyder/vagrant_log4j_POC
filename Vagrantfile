Vagrant.configure("2") do |config|
    config.vm.define "vic" do |vic|
        config.vm.hostname = "log4j_victim"
        config.vm.box = "brent-spyder/log4j_vulnerable"
        config.vm.network "forwarded_port", guest:8080, host:8080
    end
    config.vm.define "attk" do |attk|
    end
end