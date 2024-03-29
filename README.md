# Readme

## About

This repo is used for setting up a Ubuntu-based dev environment using Ansible. The playbook was tested using Ansible 2.9.

Consider backing up your dotfiles (like .bashrc) before running the playbook.

## Preparation

- Install ansible and ansible-galaxy
- Install community collection: `ansible-galaxy collection install community.general`
- Then: `ansible-galaxy install -r requirements.yml`

## Running the playbook

Run on a local machine:

```sh
ansible-playbook --ask-become-pass -i inventory.ini play.yaml

# Running additional roles (only necessary when overriding default variables)
ansible-playbook play.yaml --ask-become-pass -i inventory.ini --extra-vars "install_neovim=true"
```

## Pre-commit hooks

- This repo uses the [pre-commit](https://pre-commit.com/) framework.
- The hooks are defined and managed in [.pre-commit-config.yaml](./.pre-commit-config.yaml)
- Installation via python using pipx: `pipx install pre-commit`
- Usage:
  - To run ansible-lint manually: `pre-commit run ansible-lint`
  - To commit without running hooks: `git commit --no-verify -m ...`
