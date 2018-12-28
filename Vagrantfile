VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define 'abiquotesting' do |t|
  end
  config.vm.provider :digital_ocean do |provider, override|
    override.ssh.private_key_path = '~/.ssh/id_rsa'
    override.vm.box = 'digital_ocean'
    override.vm.box_url = 'https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box'
    override.vm.hostname = 'abiquotesting'
    provider.image = 'CentOS 6.5 x64'
    provider.region = 'Amsterdam 2'
    provider.size = '2GB'
    provider.ssh_key_name = 'VAGRANT'
    provider.client_id = 'PUT YOUR DigitalOcean CLIENT_ID HERE'
    provider.api_key = 'PUT YOUR DigitalOcean API_KEY HERE'
  end
end
