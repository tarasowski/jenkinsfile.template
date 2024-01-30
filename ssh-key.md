A .pem file is a type of private key. If your mvpfoundry key is a .pem file, that's what you'll upload to the Ansible master.

Here's how you can do it:

1. Copy your mvpfoundry.pem private key from your local machine to the Ansible master. You can use scp for this:

`scp /path/to/mvpfoundry.pem user@ansible-master:/home/user/.ssh/`

3. On the Ansible master, set the correct permissions for the key:

`chmod 600 /home/user/.ssh/mvpfoundry.pem`

(The chmod 600 command sets the permissions on the key file so that only the owner of the file can read and write it, and nobody else can access it. This is a security measure. SSH keys are sensitive data and can be used to gain unauthorized access to servers if they fall into the wrong hands. By setting the permissions to 600, you're ensuring that other users on the system can't read your private key.)

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
