# Vagrant and Ansible Templates

A template Vagrantfile and associated Ansible playbook with some of my most commonly used configurations / directives.


## Using the Vagrant-based Development Environment

You'll need [VirtualBox](https://www.virtualbox.org/wiki/Downloads), [Vagrant](http://www.vagrantup.com/downloads.html), and [Ansible](https://devopsu.com/guides/ansible-mac-osx.html) installed to use this environment.

Additionally, the following plugin is useful to keep the VirtualBox Guest Additions in sync with the base box:

	vagrant plugin install vagrant-vbguest


Fire up the Vagrant VM:
	
	vagrant up

Ensure Ansible has run successfully and provisioned the boxes.  If not, try again using `vagrant provision`

## Debugging

If you're having trouble with Vagrant, try enabling Vagrant's logging to see what's going on: `export VAGRANT_LOG=info`

## Links

Vagrant documentation: http://docs.vagrantup.com/v2/

Other useful notes: https://gist.github.com/dergachev/3866825