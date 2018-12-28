## Testing environment deploy automation

- Aimed to test Abiquo API Ruby gem
- DigitalOcean as hosting provider
- Vagrant for provisioning
- Ansible for application deployment

This repository provides a testing environment deploy to DigitalOcean of an Abiquo 3.0 Monolithic.

## Dependencies

- ansible
- python-pip
- python dopy package
- ruby >= 1.9.1
- json ruby gem
- vagrant
- vagrant-digitalocean plugin

## Instalation sample in Ubuntu x64

      # wget https://dl.bintray.com/mitchellh/vagrant/vagrant_1.6.3_x86_64.deb
      # dpkg -i vagrant_1.6.3_x86_64.deb 
      # apt-get install ansible
      # apt-get install python-pip
      # pip install dopy
      # curl -sSL https://get.rvm.io | bash -s stable --ruby
      # source /usr/local/rvm/scripts/rvm
      # gem install json
      # vagrant plugin install vagrant-digitalocean

## Environment deploy setup

Once all required dependencies are resolved, you just need to modify Vagrantfile with suitable values.
Basically, specify adequate ssh private key path, ssh_key_name to be created in DigitalOcean and
specify your DigitalOcean client_id and api_key .
You will also need to specify client_id and api_key in ./abiquo-monolithic/digital_ocean.ini file.

You can also change VM size and region, but minimum RAM amount for running Abiquo is 2GB.

Now, you are ready to run Abiquo api Ruby gem tests:

This command will create the droplet

      # vagrant up --provider=digital_ocean

This command will install an Abiquo 3.0 Monolithic instance

      # ansible-playbook -i ./abiquo-monolithic/digital_ocean.py ./abiquo-monolithic/abiquo-monolithic.yml

------
RUN TESTS
------

This command will destroy the droplet

      # vagrant destroy
