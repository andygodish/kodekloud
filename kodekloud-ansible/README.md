# NOTES: 

`ansible target1 -m ping -i inventory.txt`
`ansible target2 -m ping -i inventory.txt`

Ansible is agentless, meaning that no additional software needs to be installed on target machines. Instead, ansible establishes connectivity to its targets via ssh.

### Ansible Inventory

##### Inventory Files

INI formatted document (.ini)

alias can be prefixed before all inventory parameters (ansible_host, ansible_user, etc)

	ex: `web ansible_host=server1.company.com ...`

	refer to docs for list of inventory parameters

##### Playbooks

written in yaml

hosts
name
tasks
- list of tasks

Run a playbook: `ansible-playbook <playbook>.yaml

##### Modules

tasks: 
- name 
  <module>

ex: `yum`, `script`, etc

Tons of modules available out of the box --- see docs

	or `ansible-doc -i`

##### Additional notes:

when working with local host, do not try to define inside your hosts/inventory.ini file. Ansible will no to reference automatically inside playbooks when `localhost` is listed in the hosts section.
