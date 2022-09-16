Below are the instructions for installing Kubernetes on Ubuntu 2204 
using Ansible.  These instructions have been made as simple as possible.

# Installation Instructions

(1) Install Ansible

apt install ansible

(2) Update configuration using ansible-pull

sudo ansible-pull -k -i localhost -U https://github.com/rbrockway/ansible.git test/playbooks/ansible/main.yml

It's essentual for ansible-pull to be able to run sudo without an interactive password.  In a default 
configuration the use of sudo here pre-authenticates sudo for five minutes.
