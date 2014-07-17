# Deploying Prestashop using Ansible

This is an ansible playbook for deploying Prestashop on a Virtual Machine using Vagrant.

What gets intalled:

* Common packages i.e. fail2ban, unattended-upgrades, logwatch, checkrootkit etc ... (see 'common' role)
* Python, Pip and VirtualEnv
* PHP 5
* Apache webserver
* MySQL database
* The latest version of Prestashop


Note: This playbook is used only for the local development! **This is not production ready playbook**

## First things first

Start the vagrant environment

    $ vagrant up

## Single step deployment

Install prestashop, mysql and apache using single command

    $ ansible-playbook -i development site.yml --user vagrant --private-key=~/.vagrant.d/insecure_private_key --sudo -vvvv

## Multiple steps deployment

Run for the first time (bootstrap)

    $ ansible-playbook -i development site.yml --user vagrant --private-key=~/.vagrant.d/insecure_private_key --sudo --tags=common

Install Apache (after bootstrapping)

    $ ansible-playbook -i development site.yml --user deploy  --private-key=~/.vagrant.d/insecure_private_key --sudo --tags=apache

Install Mysql and bootstrap 'prestashop' user as well as 'prestashop' database

    $ ansible-playbook -i development site.yml --user deploy --private-key=~/.vagrant.d/insecure_private_key --sudo --tags=mysql

Install and provision prestashop

    $ ansible-playbook -i development site.yml --user deploy --private-key=~/.vagrant.d/insecure_private_key --sudo --tags=prestashop