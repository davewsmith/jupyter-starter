# Jupyter Starter

Set up a VirtualBox VM with a Jupyter Labs server and basic Python3 Data Science libraries.


## Requirements

Building the VM requires VirtualBox and Vagrant

    sudo apt-get install virtualbox

gets you the former. `http://vagrant.io` gets you the latter.

## Building the VM

    vagrant up

Depending on various factors (moon, tailwind, internet provider) provisioning and starting the VM takes between 8 and 20 minutes on my laptop.

Edit `Vagrantfile` to customize which packages get installed at VM build time.

## Running the Jupyter Labs server

With a VM running,

    vagrant ssh
    cd /vagrant
    ./runserver

The latter will report out a URL that includes a login token. Copy that URL and paste it into a browser to get to the Jupyter UI.

By default, `runserver` will use the directory `./notebooks` for notebooks.
This directory is in `.gitignore`, so that you can keep it in a separate git repository.
If you would rather keep everything in one repo, remove the entry in `.gitignore`.

To specify an alternate notebook directory, use

    ./runserver path/to/notebooks

## Stopping the Jupyter Labs server

From a browser, select `File / Shut Down`.

Or, from inside the VM, `^C` stops the server.

## Stopping and restarting the Virtual Machine

From outside the VM, `vagrant suspect` will suspend a VM, and `vagrant resume` will reactivate it.

Alternatively, `vagrant halt` to stop it entirely, and `vagrant up` to bring it back to life.

Do one of these before you reboot your laptop/server.
VirtualBox is fairly intolerant of being stopped suddenly,
and you might have to `vagrant destroy` / `vagrant up` to provision a fresh VM.

## License

None. There's nothing original here.
