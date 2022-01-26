# Playbook To Install Docker on Debian Stretch

This playbook will install Docker an Debian Stretch machine.
It is based on [Digital Ocean's How to Use Ansible to Install and Set Up Docker on Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-use-ansible-to-install-and-set-up-docker-on-ubuntu-18-04). It uses vagrant as a virtual host provider.
Single Container will be created with the options specified in the `vars/default.yml` variable file.

## Vagrant

[Vagrant](https://www.vagrantup.com/docs) - the command line utility for managing the lifecycle of virtual machines. To know more about vagrant and provisioning visit the docs page.

## Settings

- `create_containers`: number of containers to create.
- `default_container_name`: default name for new containers.
- `default_container_image`: default image for new containers.

## Running this Playbook

Quick Steps:

### 1. Obtain the playbook

```shell
git clone https://github.com/shra012/Ansible-Playbooks.git
cd Ansible-Playbooks/docker-debian
```

### 2. Bring the vagrant debian stretch up.

```shell
vagrant up
```

### 3. Customize Vagrant Options

```shell
nano Vagrantfile
```

### 3. Customize Vars

```shell
nano provisioning/vars/default.yml
```

```yml
#provisioning/vars/default.yml
---
create_containers: 1
default_container_name: docker-example
default_container_image: hello-world
```

### 4. Alter Ansible Options

```shell
nano provisioning/ansible.cfg
```

### 4. Run the Playbook

```command
cd provisioning
ansible-playbook playbook.yml
```
