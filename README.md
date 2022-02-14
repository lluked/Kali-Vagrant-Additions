# Kali-Vagrant-Additions
Additions to Kali Vagrant box provisioned with Ansible.

Ansible Roles configure:

- UK Keyboard
- Volatility (Installed under venv with symlimk /usr/local/bin/vol.py)
- Volatility3 (Installed under venv with symlimk /usr/local/bin/vol3.py)
- VS Code

Along with an Ansible task to clone MemLabs repo to home folder and setup suggested packages. More info on MemLabs available at https://github.com/stuxnet999/MemLabs.

Box is restarted after provisioning.
