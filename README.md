# Mac Setup
Ansible setup for my Mac

## Usage
The following steps will install dependencies and run the installation steps.

### Install Xcode

```
xcode-select --install
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
ansible-playbook playbooks/workstation-mba2011.yaml --ask-become-pass
```
