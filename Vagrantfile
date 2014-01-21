require 'yaml'

vconfig = YAML::load_file("doConfig")

Vagrant.configure('2') do |config|
  config.ssh.username = 'hide'

  config.vm.define :VagrantedMachine do |t|
  end

  config.vm.provider :digital_ocean do |provider, override|
    override.ssh.private_key_path = '~/.ssh/id_rsa'
    override.vm.box = 'digital_ocean'
    override.vm.box_url = "https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box"

    provider.client_id = vconfig['client_id']
    provider.api_key = vconfig['api_key']
    provider.image = 'Ubuntu 13.04 x64'
    provider.region = 'New York 2'
    provider.size = '512MB'
    provider.ca_path = '/usr/local/opt/curl-ca-bundle/share/ca-bundle.crt'
  end

  config.berkshelf.enabled = true
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "/vagrant/site-cookbooks"
    chef.roles_path = "/vagrant/roles"
    chef.data_bags_path  = "/vagrant/data_bags"

    chef.add_recipe "mysql"
  end
end

