# Atlassian Ansible Playbooks

This repository houses some work-in-progress and proof-of-concept
Ansible playbooks for installing and managing Atlassian products.

There are also Vagrant configurations to allow testing of the Ansible
playbooks. To use one just symlink to the relevant one, e.g.

    ln -s bamboo-Vagrantfile Vagrantfile

Then run `vagrant up`.

Both Stash and Bamboo will be bound to [http://localhost:8085/].

Some configuration may be required; notes on individual applications
follow:

## Bamboo

### License

Bamboo will require a license key to set when you first connect to the
web interface. This can be retrieved from [https://my.atlassian.com/].

### Database

The Ansible playbook installs a PostgreSQL database. You do not have
to use this; if not you can just select `Express Installation`.

If you do use the PostgreSQL DB, the default setting are fine, just
add the username `bamboo`.

### Agent

By default the playbook does not install an agent. If you want to
experiment with this feature then just uncomment the `bamboo-agent`
line in `bamboo-vagrant.yml`.

## Stash

The Stash playbook is more advanced and can completely configure
Stash. This requires supplying some information to the playbook:

### License

The Stash playbook can install its own license once you retrieve it
from [https://my.atlassian.com/]; set this in `stash-vagrant.yml`.

### Password

The admin password can also be set here in `stash-vagrant.yml`.
