# -*- mode: ruby -*-
# vim: set ft=ruby :

MACHINES = {
  :server => {
        :box_os => "centos/7",
        :ip_addr => '192.168.20.10',
        :memory => "1024",
  },
  :client => {
        :box_os => "centos/7",
        :ip_addr => '192.168.20.11',
        :memory => "1024",
  },

}

Vagrant.configure("2") do |config|
 config.vm.box_check_update = true
 config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.become = "true"
  end

  MACHINES.each do |boxname, boxconfig|
      config.vm.define boxname do |box|
          box.vm.box = boxconfig[:box_os]
          box.vm.host_name = boxname.to_s
          box.vm.network "private_network", ip: boxconfig[:ip_addr]
          box.vm.provider "virtualbox" do |vb|
           vb.name = boxname.to_s
           vb.memory = boxconfig[:memory]
          end
      end
  end
end