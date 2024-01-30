```
ansible_project/
├── ansible.cfg
├── inventory.ini
├── playbooks/
│   ├── setup_webserver.yml
│   ├── setup_database.yml
│   └── deploy_application.yml
├── group_vars/
│   └── all.yml
└── roles/
    ├── common/
    │   ├── tasks/
    │   │   └── main.yml
    │   ├── handlers/
    │   │   └── main.yml
    │   ├── files/
    │   └── templates/
    ├── webserver/
    │   ├── tasks/
    │   │   └── main.yml
    │   ├── handlers/
    │   │   └── main.yml
    │   ├── files/
    │   └── templates/
    └── database/
        ├── tasks/
        │   └── main.yml
        ├── handlers/
        │   └── main.yml
        ├── files/
        └── templates/
```
