### Dependencies

This playbook uses Ansible's EdgeOS plugin. It requires an installation step before use. From Ansible's documentation:

> This plugin is part of the community.network collection (version 1.3.0). To install it use: `ansible-galaxy collection install community.network`. To use it in a playbook, specify: community.network.edgeos_command.

---------------------------------------------------------
### Playbook Descriptions

The `bootstrap` playbook is to be run only once immediately after the router is made available on the network. A username and password will be required for the root account. This playbook will install the ansible service account credentials and disable the root account password.

The `deploy` playbook should be run after bootstrapping. It will install ssh keys for admins (or remove them), install Prometheus Node Exporter,

The `configure` playbook does nothing but backup the existing config and then deploy the new config found at `roles/config/files/edgeos.cfg`

To make a backup without deploying a new config, run the `backup` playbook.

-----------------------------------------------------
### Playbook Run Commands

To run the bootstrap playbook only, you will need to provide a username and password and a target host like this `ansible-playbook -u username -k -i inventory`

To run all other playbooks, you will simply need to run the playbook and specify the inventory like this `ansible-playbook -i inventory playbook-deploy.yml`
