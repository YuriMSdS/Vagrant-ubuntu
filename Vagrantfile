Vagrant.configure("2") do |config|

  config.vm.define "vagrantVM" do |machine|
    machine.vm.hostname = "vagrantVM.local"
    machine.vm.synced_folder "./shared-files", "/vagrant_data"
    machine.vm.box = "ubuntu/focal64"
    machine.vm.network "public_network", bridge: "en0: Wi-Fi"
    
    machine.vm.provider "virtualbox" do |vb|
      vb.name = "VagrantVM1"    
      vb.memory = 1024               
      vb.cpus = 1            
    end
  end
end