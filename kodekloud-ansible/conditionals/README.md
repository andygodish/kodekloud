# Conditionals 

Example: make a playbook that works to install packages in both debian and redhat based systems. The key here is that the debian based hosts will need to utilize the apt module whereas the redhat systems will use the yum ansible module. 

```
-
    name: 'Add name server entry if not already entered'
    hosts: localhost
    tasks:
        -
            shell: 'cat /etc/resolv.conf'
            register: command_output
        -
            shell: 'echo "nameserver 10.0.250.10" >> /etc/resolv.conf'
            when: 'command_output.stdout.find("10.0.250.10") == -1' 
```

- Note how we are registering the output of our first command to a variable called `command_output` and how that variable is being referenced in the play's second task.
