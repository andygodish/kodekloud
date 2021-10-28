# Modules

### command module

Executes a command on a remote node. 

Accepts parameters; example: `chdir` - cd into dir before command is run

`command: cat resolv.conf chdir=/etc` --- why is this better than `command: cat /etc/resolv.conf`?

The command module allows a `free_form` parameter, meaning that a raw command like, `cat /what.ever` can be used, as opposed to a key=value type parameter stipulation.

### script module

When you want to run a script (located on the controll node), ansible will take care of first copying the script to the remote nodes automatically. 

### service module

Start various services in a particular order. No free form input on this one. 

Parameter: state=`start` vs `started` --- ansible is ensuring that the service is started, it is not starting the service. Keep this distinction in mind. This establishes idempotency.

Ex: if httpd is aready started, => do nothing 

### lineinfile

Adds a new line to a particular file. Idempotent, ie will not keep adding the same line to the same file.  
