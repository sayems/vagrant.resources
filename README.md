# Vagrant

Create and configure lightweight, reproducible, and portable development environments. Vagrant is an amazing tool for managing virtual machines via a simple to use command line interface.

&nbsp;


## Table of contents
- [Getting Started](#getting-started)
- [Setup Kubernetes with Vagrant](https://github.com/sayems/kubernetes.resources/tree/master/k8s-vagrant)
- [Usage](#usage)
- [Connect to Vagrant box](#connect-to-vagrant-box)
    - [SSH Config](#ssh-config)


&nbsp;


Getting Started
--
Vagrant uses [Virtualbox](https://www.virtualbox.org/) to manage the virtual dependencies. You can [directly download virtualbox](https://www.virtualbox.org/wiki/Downloads) and install or use homebrew for it.

```
$ brew cask install virtualbox
```

Now install Vagrant either [from the website](http://www.vagrantup.com/downloads.html) or use homebrew for installing it.

```
$ brew cask install vagrant
```

[Vagrant-Manager](http://vagrantmanager.com/) helps you manage all your virtual machines in one place directly from the menubar.

```
$ brew cask install vagrant-manager
```


&nbsp;

[top](#table-of-contents)

&nbsp;


Usage
--

Now lets start the Vagrant box. The following DevOps tools will be automatically install in your Vagrant box.
- [Terraform](https://www.terraform.io/)
- [AWS CLI](https://aws.amazon.com/cli/)
- [Ansible](https://www.ansible.com/)


Navigate to the root ```/vagrant.resources/``` directory and then run the following command to start the Vagrant:

```bash
$ cd vagrant.resources
$ vagrant up
```

You can ssh into the machine now.
```
$ vagrant ssh
```

Login and password for most of Vagrant boxes are
```
Username : vagrant
Password : vagrant
```

Halt the vagrant machine now.
```
$ vagrant halt
```
Other useful commands are ```suspend```, ```destroy``` etc.


&nbsp;

[top](#table-of-contents)

&nbsp;


Connect to Vagrant box
--

If you want to connect to your vagrant box then you would connect to it in the following way.
```
ssh vagrant@192.168.50.10 -i ~/.vagrant.d/insecure_private_key -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no -o PasswordAuthentication=no -o IdentitiesOnly=yes
```


&nbsp;

#### SSH Config

You can also copy ```vagrant ssh-config``` into```~/.ssh/config```. This will allow you to use ssh ```ssh k8s-1``` from anywhere.

```
$ cd ~/Vagrant
$ vagrant ssh-config >> ~/.ssh/config
```


&nbsp;

[top](#table-of-contents)

&nbsp;
