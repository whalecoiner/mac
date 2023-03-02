# Mac Setup
Ansible setup for my Mac

## Usage
The following steps will install dependencies and run the installation steps.

### Install Xcode

```
xcode-select --install
```

### Install Ansible

Run the following commands to temporarily add Python 3 to your `$PATH`:

```
export PATH="$HOME/Library/Python/3.9/bin:/opt/homebrew/bin:$PATH"
```

```
cd scripts/
./bootstrap-mac.sh
```

### Satisy any Ansible requirements

```
ansible-galaxy install -r meta/requirements.yaml
```

### Run the Ansible Playbook

```
ansible-playbook playbooks/workstation-mba2011.yaml --ask-become-pass
```
