# vi: set ft=ruby :

$provision = <<SCRIPT

sudo apt-get update

sudo apt-get install -y python3.8-venv
python3 -m venv venv
. venv/bin/activate

pip install -r requirements-scraping.txt
pip install -r requirements-datascience.txt
pip install -r requirements-vision.txt

pip install jupyterlab

SCRIPT


VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "ubuntu/focal64"  # Ubuntu 20.04
    config.vm.network "forwarded_port", guest: 8888, host: 8888

    config.vm.provider "virtualbox" do |vb|
        vb.name = "Jupyter Data Science starter"
        vb.memory = 2048
        vb.cpus = 1
    end

    config.vm.provision :shell, inline: $provision, privileged: false
end
