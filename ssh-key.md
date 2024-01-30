A .pem file is a type of private key. If your mvpfoundry key is a .pem file, that's what you'll upload to the Ansible master.

Here's how you can do it:

1. Copy your mvpfoundry.pem private key from your local machine to the Ansible master. You can use scp for this:

`scp /path/to/mvpfoundry.pem user@ansible-master:/home/user/.ssh/`

3. On the Ansible master, set the correct permissions for the key:

`chmod 600 /home/user/.ssh/mvpfoundry.pem`

5. In your Ansible playbook, specify the private key to use for SSH connections. You can do this globally in your Ansible configuration (ansible.cfg), or per-playbook by adding a vars section:

```
---
- hosts: slaves
  vars:
    ansible_ssh_private_key_file: /home/user/.ssh/mvpfoundry.pem
  tasks:
    # your tasks here
```

By doing this you don't need to create new keys
