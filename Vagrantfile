# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    hostname = "example.box"
    locale = "en_GB.UTF.8"

    # Box
    config.vm.box = "ubuntu/trusty64"

    # Forward port
    config.vm.network "forwarded_port", guest: 9991, host: 9991, host_ip: "127.0.0.1"

    # Shared folders
    config.vm.synced_folder ".", "/srv"

    # Setup
    config.vm.provision :shell, :inline => "touch .hushlogin"
    config.vm.provision :shell, :inline => "hostnamectl set-hostname #{hostname} && locale-gen #{locale}"
    config.vm.provision :shell, :inline => "apt-get update --fix-missing"
    config.vm.provision :shell, :inline => "apt-get install -q -y g++ make git curl vim-gnome build-essential cmake python-dev"
    config.vm.provision :shell, :inline => "curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
        https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim"
    config.vm.provision :shell, :inline => "wget https://raw.githubusercontent.com/lw7360/vimrc/master/.vimrc"

    # Lang
    # Provide additional packages/setup/etc

end
