# Ojective:
This is Ansible Vagrant profile for a Jenkins CI server

# Getting Started

To use the vagrant file, you will need to have done the following:

  1. Refer to this document for vagrant, ansible installation Download and Install `https://www.tecmint.com/how-to-install-vagrant-on-centos-7/`
  2. Get the source code from repository: git clone `https://github.com/henshitou/vagrant-ansible-jenkins.git`
  3. cd to vagrant-ansible-jenkins,type in `vagrant up`, and Vagrant will create a new VM, install the base box, and configure it.

### Setting up your hosts file

  1. setup your ansible roles file which store your roles
     /etc/ansible/ansible.cfg
  2. You need to modify your host machine's hosts file (Linux: `/etc/hosts`), adding the line below:

    192.168.1.200  jenkins

(Where `jenkins`) is the hostname you have configured in the `Vagrantfile`).

After that is configured, you could visit http://jenkins:8080/ in a browser, and you'll see the Jenkins home page.
