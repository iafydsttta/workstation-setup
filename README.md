# Readme

## About

This repo is used for setting up a Ubuntu-based dev environment using ansible. The playbook was tested using ansible 2.9.

Consider backing up your dotfiles (like .bashrc) before running the playbook.

## Running the playbook

Run on a local machine: 

```sh
ansible-playbook --ask-become-pass -i inventory.ini playbook.ansible.yaml
```