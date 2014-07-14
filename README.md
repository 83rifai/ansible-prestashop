Start the vagrant environment

    $ vagrant up

Run for the first time (bootstrap)

    $ ansible-playbook -i development site.yml --user vagrant --private-key=~/.vagrant.d/insecure_private_key --sudo --tags=common -vvvv

Install Apache (after bootstrapping)

    $ ansible-playbook -i development site.yml --user deploy  --sudo --tags=apache -vvvv

Install Mysql and bootstrap 'prestashop' user as well as 'prestashop' database

    $ ansible-playbook -i development site.yml --user deploy --sudo --tags=mysql -vvvv

Install and provision prestashop

    $ ansible-playbook -i development site.yml --user deploy --sudo --tags=prestashop -vvvv


Install prestashop, mysql and apache using one command

    $ ansible-playbook -i development site.yml --user vagrant --private-key=~/.vagrant.d/insecure_private_key --sudo -vvvv