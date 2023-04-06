# Mac Setup
Ansible setup for my Mac

## Usage
The following steps will install dependencies and run the installation steps.

### Install Xcode

```
xcode-select --install
```

### Generate SSH key

Create an SSH config file...

```
vim ~/.ssh/config
```
and add the following:
```
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

Generate an SSH key and add it to the key agent:
```
ssh-keygen -t ed25519 -C "charlie@workstation-mba2011"
eval "$(ssh-agent -s)"
ssh-add -K ~/.ssh/id_ed25519
```


### Install Homebrew and Ansible via setup script

```
cd scripts/
./bootstrap-mac.sh
```

### Satisfy Ansible requirements

```
ansible-galaxy install -r meta/requirements.yaml
```

### Run the Ansible Playbook

```
ansible-playbook playbooks/personal.yaml --ask-become-pass
```
