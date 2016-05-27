
Vagrant.configure(2) do |config|

    config.vm.define "prometheus" do |prometheus|
      prometheus.vm.box = "ubuntu/trusty64"
      prometheus.vm.network "private_network", ip: "10.0.0.2"

      prometheus.vm.provision "ansible" do |ansible|
        ansible.playbook = "main.yml"
        ansible.sudo = true
        ansible.inventory_path = "./inventory/vagrant.ini"
        ansible.verbose = "-vv"
      end
    end

    config.vm.provider "virtualbox" do |vb|
      vb.memory = "2404"
      vb.cpus = "2"
    end    
end