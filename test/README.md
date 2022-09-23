Below are the instructions for installing Kubernetes on Ubuntu 2204 
using Ansible.  These instructions have been made as simple as possible.

Commands to be executed start with '$' to represent the shell.

# Installation Instructions

(1) Install Ansible

$ apt install ansible

(3) Install/update using ansible-pull

$ sudo ansible-pull -k -i localhost -U https://github.com/rbrockway/ansible.git test/playbooks/ansible/main.yml

It's essentual for ansible-pull to be able to run sudo without an interactive password.  In a default 
configuration the use of sudo here pre-authenticates sudo for five minutes.

# Problems

## Minikube

Minikube does not play well with NFS mounted home directories in Linux.  If you don't know what this means then you
don't have one.  A work around is to set the home directory for Mikikube to something else:

$ sudo mkdir /srv/$USER
$ export MINIKUBE_HOME=/srv/$USER

Reference: 

https://github.com/kubernetes/minikube/issues/11022
