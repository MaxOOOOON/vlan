# -*- mode: ruby -*-
# vim: set ft=ruby :

MACHINES = {
    :inetRouter => {
        :box_name => "centos/7",
        :net => [
                  {adapter: 2, virtualbox__intnet: "inernal"},
                  {adapter: 3, virtualbox__intnet: "inernal"},
        ]
  },
    :centralRouter => {
        :box_name => "centos/7",
        :net => [
                  {adapter: 2, virtualbox__intnet: "inernal"},
                  {adapter: 3, virtualbox__intnet: "inernal"},      
                  {adapter: 4, virtualbox__intnet: "testLAN"},        ]
  },
  
    :testServer1 => {
        :box_name => "centos/7",
        :net => [
                   {adapter: 2, virtualbox__intnet: "testLAN"}, 
        ]                                 
  },
  
    :testClient1 => {
        :box_name => "centos/7",
        :net => [
                  {adapter: 2, virtualbox__intnet: "testLAN"},            
        ]
  },
    :testServer2 => {
        :box_name => "centos/7",
        :net => [
                  {adapter: 2, virtualbox__intnet: "testLAN"},            
        ]
  },
    :testClient2 => {
        :box_name => "centos/7",
        :net => [
                  {adapter: 2, virtualbox__intnet: "testLAN"},            
        ]
  }
}

Vagrant.configure("2") do |config|

  MACHINES.each do |boxname, boxconfig|

    config.vm.define boxname do |box|

        box.vm.box = boxconfig[:box_name]
        box.vm.host_name = boxname.to_s

        box.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "512"]
        end        

        boxconfig[:net].each do |ipconf|
          box.vm.network "private_network", ipconf
        end
              
        box.vm.provision :ansible do |ansible|
          ansible.playbook = "./playbook.yml"
          # ansible.verbose = true
        end

      end

  end
  
end