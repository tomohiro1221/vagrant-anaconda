# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "hashicorp/precise32"
  config.vm.provision "shell", inline: <<-SHELL
wget https://3230d63b5fc54e62148e-c95ac804525aac4b6dba79b00b39d1d3.ssl.cf1.rackcdn.com/Anaconda-2.2.0-Linux-x86.sh
anaconda=Anaconda-2.2.0-Linux-x86.sh
cd /vagrant
if [ -s $anaconda ]
then
  chmod +x $anaconda
  ./$anaconda -b -p /opt/anaconda
  cat >> /home/vagrant/.bashrc << END
  # For anaconda
  PATH=/opt/anaconda/bin:$PATH
END
else
  echo "ERROR: Anaconda installer is not found"
fi
  SHELL
end
