# Vagrant Nix Jumpbox
https://github.com/aglasson/vagrant-nix-jumpbox

Managing Linux systems from Windows made easy.  
Why not WSL? WSL is great but it's not the most portable environment if you need to reinstall, change computers or have the ability to "start fresh". Vagrant gives you a local Linux environment you can spin up on-demand with a consistent (from code) environment ready to use.  

## Features
* Spins up a Vagrant Ubuntu VM on Windows
* Adds your account (based on windows username) and your authorised keys to base vagrant VM
* Adds your private key to VM for SSH'ing to other systems

<!-- ## Known Issues
* N/A - Placeholder -->

## Installation
#### Vagrant Setup  
##### Only if vagrant not already installed  
* Install [Virtual Box](https://www.virtualbox.org/), Vagrant's preferred/default provider (hypervisor), or your [desired Vagrant provider](https://www.vagrantup.com/intro/getting-started/providers) (hypervisor)
* [Install Vagrant](https://www.vagrantup.com/intro/getting-started/install)
* `vagrant up` will usually prompt for a username and password for SMB. This is required. You can use your account with local admin privileges however I suggest adding a new local user (non-admin) with at least read privileges to the directory containing the Vagrantfile.
#### SSH Keys
* This utility expects the following SSH keys in directory `%USERPROFILE%\Documents\Keys\`
    *  %USERNAME%_private.ssh - Your OpenSSH format private key
    *  %USERNAME%_public.pub - Your OpenSSH authorized_keys format public key
* I recommend securing this directory with [Windows EFS Folder Encryption](https://www.tenforums.com/tutorials/77130-encrypt-files-folders-efs-windows-10-a.html) for key safety, default EFS settings are fine as long as you're also keeping your keys in your prefered credential vault (eg. KeyPass) elsewhere

<!-- ## Example Usage
#### Placeholder

## Intended Features
#### Major Features
* N/A

#### Minor Features
* N/A -->