# Jupyter Starter

Set up a VirtualBox VM with a Jupyter notebook server and basic Python3 Data Science libraries.


## Requirements

This was developed on a laptop running Ubuntu 14.04.

Building the VM requires VirtualBox and Vagrant

    sudo apt-get install virtualbox

gets you the former. `http://vagrant.io` gets you the latter.

## Building the VM

    vagrant up

Depending on various factors, this takes between 8 and 20 minutes on my laptop.

## Running the Jupyter notebook server

From an up'd VM

    vagrant ssh
    cd /vagrant
    ./runserver

The latter will report out a URL that includes a login token. Copy that URL and paste it into a browser to get to the notebook UI.

`^C` stops the notebook server.

## Stopping and restarting the Virtual Machine

To suspend the VM, exit to the host and

    vagrant suspend

To resume

    vagrant resume

Suspend before you reboot your laptop/server. VirtualBox is fairly intolerant of being stopped suddenly.

## Notebook files

Files are saved in `notebooks/` as JSON files with an `.ipynb` extension.

## License

None. There's nothing original here.

