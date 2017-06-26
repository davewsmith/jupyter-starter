# vi: set ft=ruby :

$provision = <<SCRIPT
sudo apt-get update

sudo apt-get install -y git

# bootstrap a recent pip3
sudo apt-get install -y python3-pip
sudo -H pip3 install --upgrade pip

# Install the basic data science add-ons
sudo -H pip3 install matplotlib numpy scipy sklearn pandas seaborn

# OpenCV provides the cv2 bindings for image manipulation
sudo -H pip3 install opencv-python

# And finally, Jupyter notebooks
sudo -H pip3 install jupyter

SCRIPT



VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "forwarded_port", guest: 8888, host: 8888

    config.vm.provider "virtualbox" do |vb|
        vb.name = "Jupyter Data Science starter"
        vb.memory = 2048
        vb.cpus = 1
    end

    config.vm.provision :shell, inline: $provision, privileged: false
end
