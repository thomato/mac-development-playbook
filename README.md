# Setup
When your run this playbook on a new Mac, make sure to install the prerequisites:

First, make sure that Brew is installed as this playbook depends on it heavily:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Before Ansible can install stuff using Brew, we first need Brew to install Ansible :)
Also, Git may need to be installed to download the playbook.
```
brew install ansible
brew install git
```

After Ansible is installed, we need to install the roles that this playbook needs:
```
ansible-galaxy install -r requirements.yml
```

Copy your `local.yml.dist` to `local.yml` and change the values in here. 

## Run run run
Now everything is good to go... RUN RUN RUN it!
```
ansible-playbook main.yml --ask-become-pass
```

Fill vars/local.yml Copy vars/local.yml.dist to vars/local.yml and change the variables to your choosing.

## What is installed?
This playbook installs:
- git
- iTerm 2

This playbook configures:

*Git*
Sets the default branch to 'main' and sets your user's name and e-mail (according to the values in `git_name` and `git_email`).

## Known problems
When some applications have been installed manually, brew may complain. Either remove the application and install again with brew, or remove the application from `vars/main.yml`.
