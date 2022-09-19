Below are the instructions for installing Kubernetes on Ubuntu 2204 
using Ansible.  These instructions have been made as simple as possible.

Commands to be executed start with '$' to represent the shell.

# Installation Instructions

(1) Install Ansible

$ apt install ansible

(2) If you are using VirtualBox follow these steps:

Make sure your VM has at least two CPUs available.

Install virtualbox inside the VM.

$ apt install virtualbox

Allow nested virtualiation.

This is necessary for VBoxManage to be available to minkube later on.

$ VBoxManage modifyvm Kubernetes --nested-hw-virt on

(2) Update configuration using ansible-pull

$ sudo ansible-pull -k -i localhost -U https://github.com/rbrockway/ansible.git test/playbooks/ansible/main.yml

It's essentual for ansible-pull to be able to run sudo without an interactive password.  In a default 
configuration the use of sudo here pre-authenticates sudo for five minutes.
