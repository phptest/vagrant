# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|

  # Env
  path = ENV["PHPTEST_PATH"] || "../"

  # Box
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  # Shared folders
  config.vm.synced_folder path, "/srv"

  # Setup
  config.vm.provision :shell, :inline => "apt-get update --fix-missing"
  config.vm.provision :shell, :inline => "apt-get install -q -y python-software-properties python g++ make git curl"
  config.vm.provision :shell, :inline => "add-apt-repository ppa:ondrej/php5 && apt-get update"
  config.vm.provision :shell, :inline => "apt-get install -q -y php5-cli php5-xdebug"
  config.vm.provision :shell, :inline => "curl -s https://getcomposer.org/installer | php"
  config.vm.provision :shell, :inline => "mv ./composer.phar /usr/local/bin/composer"
  config.vm.provision :shell, :inline => "echo 'error_reporting = E_ALL' > /etc/php5/cli/conf.d/error_reporting.ini"
  config.vm.provision :shell, :inline => "echo 'display_errors = 1' >> /etc/php5/cli/conf.d/error_reporting.ini"

end
