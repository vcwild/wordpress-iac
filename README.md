# Wordpress Infrastructure as Code

## Project requirements

Create a ssh key pair named "vagrant_id_rsa" and "vagrant_id_rsa.pub" and add it to the project root folder

```{sh}
ssh-keygen -t rsa
```

Move the public key to ./ssh-keys

```{sh}
mv vagrant_id_rsa.pub ./ssh-keys/vagrant_id_rsa.pub
```

# How to Run

## Provisioning

Source environment variables

```{sh}
. ./.env
```

Run ansible playbook

```{sh}
ansible-playbook $PROVISIONING_PATH -i $HOSTS_PATH
```