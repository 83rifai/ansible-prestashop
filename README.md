Start the vagrant environment

    $ vagrant up

Run for the first time (bootstrap)

    $ ansible-playbook -i development site.yml --user vagrant --private-key=~/.vagrant.d/insecure_private_key --sudo --tags=common -vvvv

Install Apache (after bootstrapping)

    $ ansible-playbook -i development site.yml --user deploy  --sudo --tags=apache -vvvv