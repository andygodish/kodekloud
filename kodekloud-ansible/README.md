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


