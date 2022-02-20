# Setup
When your run this playbook on a new Mac, make sure to install the prerequisites:

First, make sure that Brew is installed as this playbook depends on it heavily:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Before Ansible can install stuff using Brew, we first need Brew to install Ansible :)
```
brew install ansible
```

After Ansible is installed, we need to install the roles that this playbook needs:
```
ansible-galaxy install -r requirements.yml
```

## Run run run
Now everything is good to go... RUN RUN RUN it!
```
ansible-playbook main.yml --ask-become-pass
```

## Known problems
When some applications have been installed manually, brew may complain. Either remove the application and install again with brew, or remove the application from `vars/main.yml`.
