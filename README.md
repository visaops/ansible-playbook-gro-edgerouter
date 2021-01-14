This playbook uses Ansible's EdgeOS plugin. It requires an installation step before use. From Ansible's documentation:

> This plugin is part of the community.network collection (version 1.3.0). To install it use: ansible-galaxy collection install community.network. To use it in a playbook, specify: community.network.edgeos_command.

Each playbook can be run by using `ansible-playbook -i inventory [insert playbook here]`. It should be self-explanatory what they do.

Before making any chanfges to the router config, ansible will backup the existing config in `/roles/backups/`. 
