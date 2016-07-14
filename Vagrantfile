VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(2) do |config|

  config.vm.box = "deimosfr/debian-jessie"

  # Disable the new default behavior introduced in Vagrant 1.7, to
  # ensure that all Vagrant machines will use the same SSH key pair.
  # See https://github.com/mitchellh/vagrant/issues/5005
  config.ssh.insert_key = false

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.sudo = true
    ansible.extra_vars = { ansible_ssh_user: 'vagrant' }
    ansible.playbook = "vagrant-site.yml"
  end
end
