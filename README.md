# dev_env
## Overview
This tool is a simple developing platform based on Vagrant and Docker.

### Structure
```
.
├── README.md
├── Vagrantfile
├── docker
│   ├── data
│   │   └── index.php
│   ├── docker-compose.yml
│   ├── nginx
│   │   └── conf
│   │       └── welcome.conf
│   └── php
│       └── Dockerfile
└── provisioning
    ├── playbook.yml
    └── roles
        ├── docker
        │   └── tasks
        │       └── main.yml
        ├── misc
        │   └── tasks
        │       └── main.yml
        └── system
            └── tasks
                └── main.yml

```

## Get started
1. Run `vagrant up`
    - It may take around 30 min.
    - It will be installed the following docker images and containers

    ```bash
    - nginx
    - php
    - mysql
    ```
1. Volumes
    - Put php project files in `docker/data`
