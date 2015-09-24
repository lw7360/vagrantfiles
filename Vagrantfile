# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    version = "3.3.1"
    hostname = "iojs.box"
    locale = "en_GB.UTF.8"
    path = "iojs-v#{version}-linux-x64"

    # Box
    config.vm.box = "ubuntu/trusty64"

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
