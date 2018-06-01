# dev_env
## Overview
This tool is a simple developing platform based on Vagrant and Docker.

### Structure
```
.
├── LICENSE
├── README.md
├── Vagrantfile
├── docker
│   ├── data
│   │   ├── go
│   │   │   └── sample_project
│   │   │       └── main.go
│   │   └── php
│   │       └── sample_project
│   │           └── index.php
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
        │   └── tasks
        │       └── main.yml
        └── system
            └── tasks
                └── main.yml
```

## Get started
### Install requirements on your Host OS
1. Install [VirtualBox](http://www.oracle.com/technetwork/server-storage/virtualbox/downloads/index.html?ssSourceSiteId=otnjp)
1. Install [Vagrant](https://www.vagrantup.com/downloads.html)
1. Install [Ansible](http://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
    - macOS
    ```
    $ brew install ansible
    ```
1. Insall vagrant's plugin `vagrant-hostsupdater`
    ```
    $ vagrant plugin install vagrant-hostsupdater
    ```

### Run Vagrant 
1. Run `vagrant up`
    - It may take around 30 min.
    - It will be installed the following docker images and containers

    ```bash
    - nginx
    - php
    - mysql
    - mongo
    - go
    ```
1. Volumes
    - Put project directories into `docker/data`
        - It's separated by language
