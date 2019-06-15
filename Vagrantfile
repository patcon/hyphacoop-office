# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'digital_ocean'

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "minecraft-office" do |config|
      config.vm.provider :digital_ocean do |provider, override|
        override.ssh.private_key_path = '~/.ssh/id_rsa_macbook'
        override.vm.box = 'digital_ocean'
        override.vm.box_url = "https://github.com/devopsgroup-io/vagrant-digitalocean/raw/master/box/digital_ocean.box"
        override.nfs.functional = false
        provider.ssh_key_name = 'patcon-macbook'
        provider.token = ENV['DIGITALOCEAN_API_TOKEN']
        provider.image = 'ubuntu-16-04-x64'
        provider.region = 'tor1'
        provider.size = '1gb'
      end
  end
  config.vm.box = "base"

  config.vm.synced_folder ".", "/vagrant", type: "rsync"

  # Ansible provisioner.
  config.vm.provision "ansible_local" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "provisioning/playbook.yml"
    ansible.galaxy_role_file = "requirements.yml"
    ansible.become = true
  end
end
