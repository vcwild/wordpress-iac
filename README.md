# Wordpress Infrastructure as Code

IAC configuration playbook to stack a PHP, Apache, MySQL Server database, and a Wordpress template instance.

# How to Run

## Project requirements

- [virtualbox](https://www.virtualbox.org/) >= 5.2
- [vagrant](https://www.vagrantup.com/) >= 2.2.9
- [ansible](https://www.ansible.com/) >= 2.9.9

## Authentication

Create a ssh key pair named "vagrant_id_rsa" and "vagrant_id_rsa.pub" and add it to the project root folder

```{sh}
ssh-keygen -t rsa
```

Move the public key to ./ssh-keys

```{sh}
mv vagrant_id_rsa.pub ./ssh-keys/vagrant_id_rsa.pub
```

## Virtual Machines

Source environment variables

```{sh}
. ./.env
```

Run infrastructure setup

```{sh}
vagrant up
```

## Provisioning

Run ansible playbook

```{sh}
ansible-playbook $PROVISIONING_PATH -i $HOSTS_PATH
```
