VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|


  config.vm.host_name = "perforce-berkshelf"

  config.vm.box = "opscode-centos-6.5"
  config.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5_chef-provisionerless.box"
  config.omnibus.chef_version = :latest

  config.vm.network :public_network, :public_network => "en0: Ethernet"

  config.vm.provision :chef_solo do |chef|
    
    chef.json = {
    }

    chef.run_list = [
      "recipe[perforce::p4d]",
      "recipe[perforce::linux]"
    ]
  end
end
