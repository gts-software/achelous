# -*- mode: ruby -*-
# vi: set ft=ruby :

# Note: Detect used sendmail params with the help of strace, e.g.
# strace -f -e trace=process mail ...

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/artful64"
  config.vm.provision "file", source: ".build/dist/achelous_1.0-1_amd64.deb", destination: "achelous_1.0-1_amd64.deb"
  config.vm.provision "shell", inline: <<-SHELL
    apt-get -qq update
    dpkg -i achelous_1.0-1_amd64.deb
    apt-get -y -qq install mailutils
  SHELL
end